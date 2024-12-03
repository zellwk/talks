<script lang="ts">
	import { Code, Slide, Transition } from '@animotion/core'

	let codeHTML: ReturnType<typeof Code>
	let width = '600px'
	let cols = 3
</script>

<Slide class="Slide">
	<div>
		<Code
			lang="css"
			codes={[
				`.SimpleGrid {
  display: grid;
  grid-template-columns: repeat(var(--cols, 1), minmax(0, 1fr));
  gap: var(--gap, 1rem);
  width: 100%;
  max-width: 100%;
  margin-inline: auto;

  > *,
  > *:where(.contents) > *,
  > *:where(astro-island, astro-slot) > * {
  	grid-column: var(--start, auto) / span var(--span, 1);
  	grid-row: var(--rowstart, auto) / span var(--rowspan, 1);
  	max-width: 100%;
	}
}`
			]}
		></Code>
	</div>
</Slide>

<Slide class="Slide">
	<div class="Vertical items-center">
		<div>
			<Code
				bind:this={codeHTML}
				lang="html"
				code={`
      <div class="SimpleGrid [--cols:6]">
				<div> ... </div>
				<div class="[--span:2]"> ... </div>
				<div class="[--span:3]"> ... </div>
			</div>`}
			></Code>
		</div>

		<div>
			<Transition>
				<div class="@container" style:width>
					<div class="SimpleGrid text-center [--cols:6]">
						<div class="Demo [--span:1]">1</div>
						<div class="Demo [--span:2]">2</div>
						<div class="Demo [--span:3]">3</div>
					</div>
				</div>
			</Transition>
		</div>
	</div>
</Slide>
