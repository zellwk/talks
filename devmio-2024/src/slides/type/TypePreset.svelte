<script lang="ts">
	import { Action, Code, Slide } from '@animotion/core'

	let code: ReturnType<typeof Code>
</script>

<Slide class="Slide">
	<div class="Vertical">
		<h2>Install</h2>
		<div>
			<Code lang="shell" code={`npm install @splendidlabz/tailwind`}></Code>
		</div>

		<h2 class="mt-8">Usage</h2>
		<div>
			<Code
				bind:this={code}
				lang="javascript"
				code={`import { layouts, colors, typography } from '@splendidlabz/tailwind/presets'
        
export default {
  presets: [layouts, colors, typography]
}`}
			></Code>
		</div>
	</div>

	<Action
		do={async () => {
			await code.selectToken`typography`
		}}
	/>
</Slide>
