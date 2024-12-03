<script lang="ts">
	import { Action, Code, Slide, Transition } from '@animotion/core'

	let codeHTML: ReturnType<typeof Code>
	let width = '600px'
	let cols = 3
</script>

<Slide class="Slide">
	<h1 class="title">Why don't you use inline styles?</h1>
</Slide>

<Slide class="Slide">
	<div class="Vertical items-center">
		<div>
			<Code
				bind:this={codeHTML}
				lang="html"
				code={`
      <div class="SimpleGrid [--cols:3]">
				...
			</div>`}
			></Code>
		</div>

		<div>
			<Transition>
				<div class="Demo @container p-4" style:width>
					<div class="SimpleGrid" style="--cols:{cols}">
						<div class="Demo [--span:1]">Item 1</div>
						<div class="Demo [--span:1]">Item 2</div>
						<div class="Demo [--span:1]">Item 3</div>
						<div class="Demo [--span:1]">Item 4</div>
						<div class="Demo [--span:1]">Item 5</div>
						<div class="Demo [--span:1]">Item 6</div>
					</div>
				</div>
			</Transition>
		</div>
	</div>

	<Action
		do={async () => {
			await codeHTML.update`
			 <div class="SimpleGrid" styles="--cols: 3">
				...
			</div>
		`
		}}
	/>

	<Action
		do={async () => {
			await codeHTML.update`
			 <div class="SimpleGrid [--cols:3]">
				...
			</div>
		`
		}}
	/>

	<Action
		do={async () => {
			await codeHTML.update`
			 <div class="SimpleGrid @bp6:[--cols:3]">
				...
			</div>
		`
		}}
	/>

	<Action
		do={async () => {
			await codeHTML.update`
			 <div class="SimpleGrid @bp4:[--cols:2] @bp6:[--cols:3]">
				...
			</div>
		`
		}}
	/>

	<Transition
		do={() => {
			width = '400px'
			cols = 2
		}}
	></Transition>

	<Transition
		do={() => {
			width = '300px'
			cols = 1
		}}
	></Transition>
</Slide>
