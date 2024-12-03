<script lang="ts">
	import { Action, Code, Slide } from '@animotion/core'

	let codeTW: ReturnType<typeof Code>
	let codeTW2: ReturnType<typeof Code>
</script>

<Slide class="Slide">
	<div class="Vertical gap-6">
		<h2 class="text-center">Pseudo element</h2>
		<div
			class="relative rounded-xl
      border-4 border-[lightblue] p-6 before:absolute before:-top-7 before:-right-8 before:rounded-xl before:border-4
      before:border-[lightblue] before:bg-[#15161a]
        before:p-2 before:text-xl before:content-['Hello']"
		>
			Content
		</div>
		<div>
			<Code bind:this={codeTW} lang="html" code={``}></Code>
		</div>
		<div></div>
	</div>
	<Action
		actions={[
			async () => {
				await codeTW.update`<div class="relative rounded-xl border-4 border-[lightblue] p-6">
  Content
</div>`
			},

			async () => {
				await codeTW.update`<div
  class="relative rounded-xl border-4 border-[lightblue] p-6 
  before:absolute before:-top-7 before:-right-8 before:rounded-xl 
  before:border-4 before:border-[lightblue] before:bg-[#15161a]
  before:p-2 before:text-xl before:content-['Hello']"
>
  Content
</div>`
			}
		]}
	/>
</Slide>

<Slide class="Slide">
	<div class="Vertical gap-6">
		<h2 class="text-center">Normal element</h2>
		<div class="relative rounded-xl border-4 border-[lightblue] p-6">
			<div
				class="absolute -top-7 -right-8 rounded-xl border-4 border-[lightblue] bg-[#15161a] p-2 text-xl"
			>
				Hello
			</div>
			<div>Content</div>
		</div>
		<div>
			<Code bind:this={codeTW2} lang="html" code={``}></Code>
		</div>
	</div>

	<Action
		actions={[
			async () => {
				await codeTW2.update`<div class="relative rounded-xl border-4 border-[lightblue] p-6">
  Content
</div>`
			},

			async () => {
				await codeTW2.update`<div class="relative rounded-xl border-4 border-[lightblue] p-6">
  <div> <!-- Before element --> </div>
  <div>Content</div>
</div>`
			},

			async () => {
				await codeTW2.update`<div class="relative rounded-xl border-4 border-[lightblue] p-6">
  <div>Hello</div>
  <div>Content</div>
</div>`
			},

			async () => {
				await codeTW2.update`<div class="relative rounded-xl border-4 border-[lightblue] p-6">
  <div 
    class="absolute -top-7 -right-8 rounded-xl border-4 
    border-[lightblue] bg-[#15161a] p-2 text-xl"
  >
    Hello
  </div>
  <div>Content</div>
</div>`
			}
		]}
	/>
</Slide>
