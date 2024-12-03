<script lang="ts">
	import { Action, Code, Slide } from '@animotion/core'

	let codeHTML: ReturnType<typeof Code>
	let codeCSS: ReturnType<typeof Code>
	let codeTW: ReturnType<typeof Code>
</script>

<!-- Try to animate the last 3rd and 4th code blocks -->
<Slide class="Slide">
	<div class="SimpleGrid gap-8 [--cols:2]">
		<h2 class="text-center">HTML & CSS</h2>
		<h2 class="text-cLightBlue-500 text-center">Tailwind</h2>
		<div class="grid gap-[inherit]">
			<div>
				<Code
					bind:this={codeCSS}
					lang="css"
					code={`.Card {
					padding: 1rem;
					/* ... */
				}`}
				></Code>
			</div>
		</div>
		<div class="grid gap-[inherit]">
			<div>
				<Code bind:this={codeTW} lang="html" code={``}></Code>
			</div>
		</div>
	</div>

	<Action
		actions={[
			async () => {
				await codeTW.update`<div class="Card"> ... </div>`
			},

			async () => {
				await codeCSS.update`.Card {
  padding: 1rem;
  /* ... */
}
  
.Card-large {
  padding: 1.5rem;
  /* ... */
}`
			},

			async () => {
				await codeTW.update`<!-- 1rem padding -->
<div class="Card"> ... </div>

<!-- 1.5rem padding -->
<div class="Card p-6"> ... </div>`
			}
		]}
	/>
</Slide>
