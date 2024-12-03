<script lang="ts">
	import { Action, Code, Slide } from '@animotion/core'

	let codeHTML: ReturnType<typeof Code>
	let codeCSS: ReturnType<typeof Code>
	let codeTW: ReturnType<typeof Code>
</script>

<Slide class="Slide">
	<div class="Vertical">
		<button class="self-center bg-blue-700 p-4 text-zinc-300"> Click me </button>
		<div class="GridRepeatAuto gap-x-12 gap-y-6 [--cols:2]">
			<h2>HTML & CSS</h2>
			<h2>Tailwind</h2>
			<div class="Vertical">
				<div>
					<Code lang="html" bind:this={codeHTML} code={``} />
				</div>
				<div>
					<Code lang="css" bind:this={codeCSS} code={``} />
				</div>
			</div>

			<div>
				<Code lang="html" bind:this={codeTW} code={``} />
			</div>
		</div>
	</div>

	<Action
		actions={[
			async () => {
				await codeTW.update`<button class="bg-blue-700 text-zinc-300">
  ...
</button>`
			},

			async () => {
				await codeHTML.update`<button> ... </button>`
			},

			async () => {
				await codeCSS.update`button {
  background-color: theme('colors.blue.700');
  color: theme('colors.zinc.300');
}`
			},

			async () => {
				await codeCSS.update`button {
  background-color: var(--blue-700);
  color: var(--zinc-300);
}`
			}
		]}
	/>
</Slide>
