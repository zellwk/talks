<script lang="ts">
	import { Action, Code, Slide } from '@animotion/core'

	let code: ReturnType<typeof Code>
	let code2: ReturnType<typeof Code>
	let item: HTMLDivElement
</script>

<Slide class="Slide">
	<div class="Vertical">
		<h2>Fill System</h2>
		<div class="GridRepeatAuto [--cols:2]">
			<div>
				<Code
					lang="html"
					code={`<div class="Fill-blue"> 
	... 
</div>`}
				/>
			</div>
			<div>
				<Code
					lang="css"
					codes={[
						``,
						`.Fill-blue {
  --bg-color: var(--blue-500);
	--text-color: var(--gray-800);
	--bg-hover-color: var(--blue-600);
	--text-hover-color: var(--gray-900);
}`
					]}
				/>
			</div>
		</div>
	</div>
</Slide>

<Slide class="Slide">
	<div class="Vertical">
		<h2>Fill System</h2>
		<div>
			<Code
				bind:this={code}
				lang="css"
				code={`[class*='Fill'] {
  border-color: var(--border-color);
  color: var(--text-color);
  background-color: var(--bg-color);
}`}
			/>
		</div>
	</div>

	<Action
		do={async () => {
			await code.update`[class*='Fill'] {
  border-color: var(--border-color);
  color: var(--text-color);
  background-color: var(--bg-color);

  &:hover {
    border-color: var(--border-hover-color, var(--border-color));
    color: var(--text-hover-color, var(--text-color));
    background-color: var(--bg-hover-color, var(--bg-color));
  }
  
  &:focus {
    border-color: var(--border-focus-color, var(--border-color));
    color: var(--text-focus-color, var(--text-color));
    background-color: var(--bg-focus-color, var(--bg-color));
  }
}`
			await code.selectLines`6-16`
		}}
	/>

	<Action
		do={async () => {
			await code.update`[class*='Fill'] {
  /* ... */

  &:focus {
    border-color: var(
      --border-focus-color,
      var(--border-hover-color, var(--border-color))
    );
    color: var(
      --text-focus-color,
      var(--text-hover-color, var(--text-color))
    );
    background-color: var(
      --bg-focus-color,
      var(--bg-hover-color, var(--bg-color))
    );
  }
}`
			await code.selectLines`6, 10, 14`
		}}
	/>
</Slide>

<Slide class="Slide">
	<div class="Vertical">
		<div>
			<Code
				lang="html"
				codes={[
					`<button 
  class="bg-blue-500 text-gray-800 
  hover:bg-blue-600 hover:text-gray-900 
  focus:bg-blue-600 focus:text-gray-900"
> 
  ... 
</button>`,
					`<button class="Fill-blue"> ... </button>`
				]}
			></Code>
		</div>
		<button class="Fill-blue self-center"> Click me </button>
	</div>
</Slide>

<Slide class="Slide">
	<div class="GridRepeatAuto gap-6 [--cols:2]">
		<div class="text-4xl">
			<Code
				lang="css"
				codes={[
					`.Fill-blue-outline {
  --text-color: var(--blue-500);
  --border-color: var(--blue-500);
	--text-hover-color: var(--blue-600);
	--border-hover-color: var(--blue-600);
}`
				]}
			></Code>
		</div>
		<button class="Fill-blue-outline self-center"> Outline </button>

		<div class="text-4xl">
			<Code
				lang="css"
				codes={[
					`.Fill-blue-light {
  --bg-color: var(--blue-900);
  --text-color: var(--gray-200);
  --border-color: var(--blue-500);
	--bg-hover-color: var(--blue-800);
}`
				]}
			></Code>
		</div>
		<button class="Fill-blue-light self-center"> Light </button>

		<div class="text-4xl">
			<Code
				lang="css"
				codes={[
					`.Fill-blue-heavy {
	--bg-color: var(--blue-500);
	--text-color: var(--gray-800);
	--bg-hover-color: var(--blue-600);
}`
				]}
			></Code>
		</div>
		<button class="Fill-blue self-center"> Heavy </button>
	</div>
</Slide>

<Slide class="Slide">
	<div class="Vertical">
		<h2>Fill System</h2>
		<div>
			<Code
				bind:this={code2}
				lang="css"
				code={`[class*='Fill'] { 
  /* ... */
}`}
			/>
		</div>
	</div>

	<Action
		do={async () => {
			await code2.update`[class*='Fill'] {
  /* ... */
  
  &:active { /* ... */ }

  &.selected,
  &.checked,
  &[aria-current],
  &[aria-selected],
  &[aria-expanded='true'] { /* ... */ }
}`
		}}
	/>
</Slide>
