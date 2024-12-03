<script lang="ts">
	import { Action, Code, Slide, Transition } from '@animotion/core'

	let codeHTML: ReturnType<typeof Code>
	let codeCSS: ReturnType<typeof Code>
	let example: HTMLDivElement
</script>

<Slide class="Slide">
	<div class="GridRepeatAuto gap-6 [--cols:2]">
		<Transition class="Demo relative p-6 [--span:2]">
			<div bind:this={example} class="Demo Edge-topright-center p-2 text-xl">Hello</div>
			<div>Content</div>
		</Transition>

		<div>
			<Code lang="html" bind:this={codeHTML} code={``}></Code>
		</div>

		<div>
			<Code lang="css" bind:this={codeCSS} code={``}></Code>
		</div>
	</div>

	<Action
		do={async () => {
			await codeHTML.update`<div class="relative rounded-xl 
			border-4 border-[lightblue] p-6"
>
  <div
    class="absolute -top-7 -right-8 rounded-xl 
    border-4 border-[lightblue] bg-[#15161a]
    p-2 text-xl"
  >
    Hello
  </div>
  <div>Content</div>
</div>`
		}}
	/>

	<Action
		do={async () => {
			await codeCSS.update`.Demo {
	border: 4px solid lightblue;
  border-radius: 1rem;
	background-color: #15161a
}`
		}}
	/>

	<Action
		do={async () => {
			await codeHTML.update`<div class="Demo relative p-6">
  <div class="Demo absolute -top-7 -right-8 p-2 text-xl">
    Hello
  </div>
  <div>Content</div>
</div>`
		}}
	/>

	<Action
		do={async () => {
			await codeHTML.selectLines`2`
		}}
	/>

	<Action
		do={async () => {
			await codeHTML.update`<div class="Demo relative p-6">
  <div class="Demo Edge-topright-center p-2 text-xl">
    Hello
  </div>
  <div>Content</div>
</div>`
		}}
	/>

	<Action
		do={async () => {
			await codeHTML.update`<div class="Demo relative p-6">
  <div class="Demo Edge-topleft-center p-2 text-xl">
    Hello
  </div>
  <div>Content</div>
</div>`
		}}
	/>

	<Transition
		do={async () => {
			example.classList.replace('Edge-topright-center', 'Edge-topleft-center')
		}}
	/>

	<style>
		.Demo {
			border-color: lightblue;
		}
	</style>
</Slide>

<Slide class="Slide">
	<img src="/images/splendidlabz-edge.png" alt="Edge" />
</Slide>

<Slide class="Slide">
	<img src="/images/flex-grid.png" alt="Flex Grid" />
</Slide>

<Slide class="Slide">
	<h2>Subgrid</h2>
	<img src="/images/subgrid.png" alt="Subgrid" />
</Slide>

<Slide class="Slide">
	<h2>Subgrid</h2>
	<img src="/images/subgrid-ag.png" alt="Subgrid AG" />
</Slide>
