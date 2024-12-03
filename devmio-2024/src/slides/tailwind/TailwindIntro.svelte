<script lang="ts">
	import { Action, Code, Slide } from '@animotion/core'

	let codeHTML: ReturnType<typeof Code>
	let codeCSS: ReturnType<typeof Code>
	let codeTW: ReturnType<typeof Code>
</script>

<!-- Maybe animate the result out -->
<Slide class="Slide">
	<div class="SimpleGrid gap-12 [--cols:2]">
		<h2 class="text-center">HTML & CSS</h2>
		<h2 class="text-cLightBlue-500 text-center">Tailwind</h2>
		<div class="Vertical gap-inherit">
			<div>
				<Code bind:this={codeHTML} lang="html" code={``}></Code>
			</div>
			<div>
				<Code bind:this={codeCSS} lang="css" code={``}></Code>
			</div>
		</div>
		<div>
			<Code bind:this={codeTW} lang="html" code={``}></Code>
		</div>

		<!-- Result of the two code above -->
		<div class="[--span:2]">
			<div class="h-[6rem] rounded-2xl bg-[lightblue] p-4"></div>
		</div>
	</div>

	<Action
		actions={[
			async () => {
				await codeHTML.update`<div class="Card"> ... </div>`
			},

			async () => {
				await codeCSS.update`.Card {
  padding: 1rem;
  border-radius: 1rem;
  background: lightblue;
}`
			},

			async () => {
				await codeTW.update`<div class=""> ... </div>`
			},

			async () => {
				await codeTW.update`<div class="p-4"> ... </div>`
				await codeCSS.selectLines`2`
			},

			async () => {
				await codeTW.update`<div class="p-4 rounded-2xl"> ... </div>`
				await codeCSS.selectLines`2-3`
			},

			async () => {
				await codeTW.update`<div 
  class="p-4 rounded-2xl bg-[lightblue]"
> 
  ... 
</div>`
				await codeCSS.selectLines`2-4`
			}
		]}
	/>
</Slide>

<!-- async () => {
  await codeTW.update`<div class="p-4 rounded-2xl
    bg-[lightblue]"
  > 
    ... 
  </div>`
} -->
