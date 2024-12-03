<script lang="ts">
	import { Action, Code, Slide, Transition } from '@animotion/core'

	let codeHTML: ReturnType<typeof Code>
	let codeCSS: ReturnType<typeof Code>
	let codeJS: ReturnType<typeof Code>
	let example: HTMLDivElement
</script>

<Slide class="Slide">
	<div class="GridRepeatAuto [--cols:2]">
		<div class="Vertical">
			<div>
				<Code
					bind:this={codeJS}
					lang="js"
					code={`module.exports = {
  theme: {
    fontSize: {
      sm: ['14px', '20px'],
      base: ['16px', '24px'],
      lg: ['20px', '28px'],
      xl: ['24px', '32px'],
    }
  }
}`}
				></Code>
			</div>

			<div>
				<Code bind:this={codeCSS} lang="css" code={``}></Code>
			</div>
		</div>

		<div class="Vertical">
			<div>
				<Code bind:this={codeHTML} lang="html" code={``}></Code>
			</div>

			<Transition>
				<div class="text-cYellow-500" bind:this={example}></div>
			</Transition>
		</div>
	</div>

	<Action
		do={async () => {
			await codeJS.update`module.exports = {
	theme: {
		fontSize: {
			'Marvin-1': /* ... */ ,
      'Marvin-2': /* ... */,
			'Jetbrains-1': /* ... */ ,
      'Jetbrains-2': /* ... */,
		}
	}
}
		`
			await codeJS.selectLines`4-7`
		}}
	/>

	<Action
		do={async () => {
			await codeHTML.update`<div class="Marvin-1"> ... </div>`
		}}
	/>

	<Transition
		do={async () => {
			await codeHTML.update`<div class="Marvin-1"> ... </div>`
			example.textContent = 'Marvin Visions'
		}}
	/>

	<Action
		do={async () => {
			await codeJS.update`module.exports = {
  theme: {
		fontFamily: [{
			Marvin: ['Marvin Visions', 'sans-serif'],
		}],
		fontSize: {
			'Marvin-1': /* ... */ ,
			'Marvin-2': /* ... */,
			'Jetbrains-1': /* ... */ ,
			'Jetbrains-2': /* ... */,
		}
	}
}
	`
			await codeJS.selectLines`3-5`
		}}
	/>

	<Transition
		do={async () => {
			await codeHTML.update`<div class="Marvin Marvin-1"> ... </div>`
			example.classList.add('Marvin-1')
		}}
	/>

	<Transition
		do={async () => {
			await codeCSS.update`[class*="Marvin"] {
  font-family: '"Marvin Visions"', 'sans-serif';
}`
		}}
	/>

	<Transition
		do={async () => {
			await codeHTML.update`<div class="Marvin-1"> ... </div>`
		}}
	/>
</Slide>
