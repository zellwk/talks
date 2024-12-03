<script lang="ts">
	import { Action, Code, Slide, Transition } from '@animotion/core'

	let codeHTML: ReturnType<typeof Code>
	let codeCSS: ReturnType<typeof Code>
	let demo = $state('grid grid-cols-3 gap-4')
	let demoItem: HTMLDivElement
</script>

<Slide class="Slide">
	<h1 class="title">Another Example</h1>
</Slide>

<Slide class="Slide">
	<div class="SimpleGrid [--cols:2]">
		<div>
			<Code
				bind:this={codeHTML}
				lang="html"
				code={`<div class="grid grid-cols-3 gap-4">
				  <div>Item 1</div>
				  <div>Item 2</div>
				  <div>Item 3</div>
				</div>`}
			></Code>
		</div>

		<div>
			<Code bind:this={codeCSS} lang="css" code={``}></Code>
		</div>

		<div class="[--span:2]">
			<Transition>
				<div class={demo}>
					<div class="Demo [--span:1]">Item 1</div>
					<div class="Demo [--span:1]" bind:this={demoItem}>Item 2</div>
					<div class="Demo [--span:1]">Item 3</div>
				</div>
			</Transition>
		</div>
	</div>

	<Action
		do={async () => {
			await codeCSS.update`
			@layer components {

			}
		`
		}}
	/>

	<Action
		do={async () => {
			await codeCSS.update`
			@layer components {
			  .SimpleGrid {
				  display: grid;
					grid-template-columns: repeat(3, 1fr);
					gap: 1rem;
				}
			}
		`
		}}
	/>

	<Action
		do={async () => {
			await codeHTML.update`
			<div class="grid grid-cols-3 gap-4">
				<div>Item 1</div>
				<div class="w-[500px]">Item 2</div>
				<div>Item 3</div>
			</div>
		`
		}}
	/>

	<Transition
		do={() => {
			demoItem.style.borderColor = 'var(--color-cTurquoise-500)'
			demoItem.style.width = '600px'
		}}
	/>

	<Action
		do={async () => {
			await codeHTML.update`
			<div class="grid grid-cols-3 gap-4">
				<div>Item 1</div>
				<div>Item 2</div>
				<div>Item 3</div>
			</div>
		`
		}}
	/>

	<Transition do={() => (demoItem.style = '')} />

	<Action
		actions={[
			async () => {
				await codeHTML.update`
			<div 
			  class="grid grid-cols-[repeat(3,minmax(0,1fr))] gap-4"
			>
				<div>Item 1</div>
				<div>Item 2</div>
				<div>Item 3</div>
			</div>
		`
			},

			async () => {
				await codeHTML.update`
			<div 
			  class="grid grid-cols-[repeat(3,minmax(0,1fr))] gap-4"
			>
				<div class="max-w-full">Item 1</div>
				<div class="max-w-full">Item 2</div>
				<div class="max-w-full">Item 3</div>
			</div>
		`
			},

			async () => {
				await codeHTML.update`
			<div 
			  class="grid grid-cols-[repeat(3,minmax(0,1fr))] gap-4
				[&>*]:max-w-full"
			>
				<div>Item 1</div>
				<div>Item 2</div>
				<div>Item 3</div>
			</div>
		`
			}
		]}
	/>

	<Action
		do={async () => {
			await codeCSS.update`
			@layer components {
			  .SimpleGrid {
				  display: grid;
					grid-template-columns: repeat(3, minmax(0, 1fr));
					gap: 1rem;

					> * {
						max-width: 100%;
					}
				}
			}
		`
			await codeCSS.selectLines`7-9`
		}}
	/>

	<Action
		do={async () => {
			await codeCSS.selectLines`*`
			await codeHTML.update`
			<div class="SimpleGrid">
				<div>Item 1</div>
				<div>Item 2</div>
				<div>Item 3</div>
			</div>
		`
		}}
	/>

	<Action
		do={async () => {
			await codeCSS.update`
			@layer components {
			  .SimpleGrid {
				  display: grid;
					grid-template-columns: 
					  repeat(var(--cols, 1), minmax(0, 1fr));
					gap: 1rem;

				  > * {
						max-width: 100%;
					}
				}
			}
		`
			await codeCSS.selectLines`4,5`
		}}
	/>

	<Transition do={() => (demo = 'SimpleGrid [--cols:1]')} />

	<Action
		do={async () => {
			await codeHTML.update`
			<div class="SimpleGrid [--cols:3]">
				<div>Item 1</div>
				<div>Item 2</div>
				<div>Item 3</div>
			</div>
		`
		}}
	/>

	<Transition do={() => (demo = 'SimpleGrid [--cols:3]')} />

	<Action
		do={async () => {
			await codeHTML.update`
		<div class="SimpleGrid [--cols:3]">
			<div>Item 1</div>
			<div class="w-[500px]">Item 2</div>
			<div>Item 3</div>
		</div>
	`
		}}
	/>
	<Transition
		do={() => {
			demoItem.style.borderColor = 'var(--color-cTurquoise-500)'
			demoItem.style.width = '600px'
		}}
	/>
</Slide>
