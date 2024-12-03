<script lang="ts">
	import { Action, Code, Slide } from '@animotion/core'

	let codeCSS: ReturnType<typeof Code>
	let codeTW: ReturnType<typeof Code>

	let codeHTML2: ReturnType<typeof Code>
	let codeCSS2: ReturnType<typeof Code>
	let codeTW2: ReturnType<typeof Code>
</script>

<Slide class="Slide">
	<div class="SimpleGrid gap-8 [--cols:2]">
		<h2 class="text-center">CSS</h2>
		<h2 class="Tailwind text-center">Tailwind</h2>
		<div>
			<Code
				bind:this={codeCSS}
				lang="css"
				code={`.Component {
  display: flex; 
  flex-direction: column; 

  @media (width > 768px) {
    flex-direction: row;
  }
}`}
			></Code>
		</div>

		<div>
			<Code bind:this={codeTW} lang="html" code={``}></Code>
		</div>
	</div>

	<Action
		actions={[
			async () => {
				await codeTW.update`<div class="flex"> ... </div>`
				await codeCSS.selectLines`2`
			},
			async () => {
				await codeTW.update`<div class="flex flex-col"> ... </div>`
				await codeCSS.selectLines`2,3`
			},
			async () => {
				await codeTW.update`<div class="flex flex-col md:flex-row"> 
  ... 
</div>`

				await codeCSS.selectLines`2-7`
			}
		]}
	/>
</Slide>

<Slide class="Slide">
	<div class="SimpleGrid gap-8 [--cols:2]">
		<h2 class="text-center">CSS</h2>
		<h2 class="Tailwind text-center">Tailwind</h2>
		<div class="Vertical">
			<div>
				<Code lang="html" bind:this={codeHTML2} code={`<div class="Component"> ... </div>`}></Code>
			</div>
			<div>
				<Code
					bind:this={codeCSS2}
					lang="css"
					code={`.Component {
  display: flex; 
  flex-direction: column; 

  @container (inline-size > 768px) {
    flex-direction: row;
  }
}`}
				></Code>
			</div>
		</div>

		<div>
			<Code
				bind:this={codeTW2}
				lang="html"
				code={`<div class="flex flex-col md:flex-row"> 
  ... 
</div>`}
			></Code>
		</div>
	</div>

	<Action
		actions={[
			async () => {
				await codeCSS2.update`.Container {
  container-type: inline-size;
}

.Component {
  display: flex; 
  flex-direction: column; 

  @container (inline-size > 768px) {
    flex-direction: row;
  }
}`
			},

			async () => {
				await codeHTML2.update`<div class="Container">
  <div class="Component"> ... </div>
</div>`
			},

			async () => {
				await codeTW2.update`<div class="@container">
  <div class="flex flex-col md:flex-row"> 
    ... 
  </div>
</div>`
			},

			async () => {
				await codeTW2.update`<div class="@container">
  <div class="flex flex-col @md:flex-row"> 
    ... 
  </div>
</div>`
			}
		]}
	/>
</Slide>
