<script lang="ts">
	import { Action, Code, Slide, Transition } from '@animotion/core'

	let code: ReturnType<typeof Code>
	let item: HTMLDivElement
</script>

<Slide class="Slide">
	<div class="Vertical">
		<div>
			<Code bind:this={code} lang="svelte" code={`<div class="border-blue-500"> ... </div>`}></Code>
		</div>

		<Transition>
			<div class="Demo" bind:this={item}>Item</div>
		</Transition>
	</div>

	<Action
		do={async () => {
			await code.update`<div class=\`border-$\{dynamic\}-500\`> ... </div>`
		}}
	/>

	<Action
		do={async () => {
			await code.update`<div style=\`border-color: var(--$\{dynamic\-500})\` > ... </div>`
		}}
	/>

	<Action
		do={async () => {
			await code.update`<script>
  let dynamic = 'pink'
</script>

<div style=\`border-color: var(--$\{dynamic\-500})\` > ... </div>`
		}}
	/>

	<Transition do={async () => (item.style.borderColor = 'pink')} />
</Slide>
