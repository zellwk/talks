<script lang="ts">
	import { Action, Code, Slide, Transition } from '@animotion/core'

	let codeHTML: ReturnType<typeof Code>
	let codeCSS: ReturnType<typeof Code>
	let demo = $state('Vertical')
</script>

<Slide class="Slide">
	<h1 class="title">Example</h1>
</Slide>

<Slide class="Slide">
	<div class="GridRepeatAuto gap-6 [--cols:2]">
		<div class="Vertical gap-inherit">
			<div>
				<Code bind:this={codeHTML} lang="html" code={`<div class="flex flex-col gap-4"> ... </div>`}
				></Code>
			</div>

			<div class="Stack">
				<Transition>
					<div class={demo}>
						<div class="Demo">Item 1</div>
						<div class="Demo">Item 2</div>
						<div class="Demo">Item 3</div>
					</div>
				</Transition>
			</div>
		</div>
		<div>
			<Code bind:this={codeCSS} lang="css" code={``}></Code>
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
			  .Vertical {
				  display: flex;
					flex-direction: column;
					gap: 1rem;
				}
			}
		`
		}}
	/>

	<Action
		do={async () => {
			await codeHTML.update`<div class="Vertical"> ... </div>`
		}}
	/>

	<Action
		do={async () => {
			await codeHTML.update`<div class="Vertical @bp4:flex-row"> ... </div>`
		}}
	/>

	<Transition do={() => (demo = 'Horizontal')} />

	<Action
		do={async () => {
			await codeCSS.update`
			@layer components {
			  .Vertical {
				  display: flex;
					flex-direction: column;
					gap: 1rem;
				}

				.Horizontal {
				  display: flex;
					flex-direction: row;
					gap: 1rem;
				}
			}
			`
		}}
	/>

	<Action
		do={async () => {
			await codeHTML.update`<div class="Vertical @bp4:Horizontal"> ... </div>`
		}}
	/>
</Slide>
