<script lang="ts">
	import { Code, Presentation, Slide, Transition } from '@animotion/core'
	import { Masonry } from '@splendidlabz/layouts/scripts'
	import { SVG } from '@splendidlabz/svelte'
	import { onMount } from 'svelte'
	import CreateCompsGrid from '../slides/CreatingComponents/Grid.svelte'
	import CreateCompsGrid2 from '../slides/CreatingComponents/Grid2.svelte'
	import CreateCompsHorizontalAndVertical from '../slides/CreatingComponents/HorizontalAndVertical.svelte'
	import CreateCompsInlineStyle from '../slides/CreatingComponents/InlineStyle.svelte'
	import CreateCompsLogic from '../slides/CreatingComponents/Logic.svelte'
	import More from '../slides/CreatingComponents/More.svelte'
	import ColorIntro from '../slides/colors/ColorIntro.svelte'
	import ColorPreset from '../slides/colors/ColorPreset.svelte'
	import DynamicColors from '../slides/colors/DynamicColors.svelte'
	import FillPlugin from '../slides/colors/FillPlugin.svelte'
	import FillSystem from '../slides/colors/FillSystem.svelte'
	import Tools from '../slides/intro/Tools.svelte'
	import AdjustValues from '../slides/tailwind/AdjustValues.svelte'
	import PseudoElements from '../slides/tailwind/PseudoElements.svelte'
	import ResponsiveModifiers from '../slides/tailwind/ResponsiveModifiers.svelte'
	import TailwindIntro from '../slides/tailwind/TailwindIntro.svelte'
	import ChooseFontSize from '../slides/type/ChooseFontSize.svelte'
	import FluidVsResponsive from '../slides/type/FluidVsResponsive.svelte'
	import ResponsiveType from '../slides/type/ResponsiveType.svelte'
	import ResponsiveType2 from '../slides/type/ResponsiveType2.svelte'
	import TypeTailwind from '../slides/type/TypeTailwind.svelte'
	import TypeTailwind2 from '../slides/type/TypeTailwind2.svelte'

	onMount(() => {
		Masonry()
	})
</script>

<Presentation options={{ history: true, transition: 'fade', controls: false, progress: false }}>
	<Slide class="Slide">
		<div class="Stack">
			<h1 class="HeroHeading max-w-[70rem] gap-0">
				<span class="Eyebrow SASuperhero !text-light text-[3rem]">My journey to</span>
				<span class="text-[10rem]"
					>Loving <span class="Tailwind">Tailwind</span> and <span class="CSS">CSS</span>
				</span>
			</h1>

			<div class="Marvin-light SASuperhero Pos-bottomleft top-[6.5rem] w-full gap-2 [--cols:2]">
				<div class="Horizontal justify-between">
					<div class="Vertical">
						<div class="Horizontal items-center">
							<SVG icon="logos:twitter" />
							<a href="https://x.com/zellwk" target="_blank">@zellwk</a>
						</div>

						<div class="Horizontal items-center">
							<SVG icon="twemoji:butterfly" />
							<a href="https://x.com/zellwk" target="_blank">@zellwk.bsky.social</a>
						</div>
					</div>
					<img class="h-auto w-[300px]" src="/images/devmio.png" alt="" />
				</div>
			</div>
		</div>
	</Slide>

	<Slide class="Slide">
		<div class="SASuperhero">
			<p>You will:</p>
			<ol>
				<Transition order={1}>
					<li>Rethink how you use Tailwind</li>
				</Transition>
				<Transition order={2}>
					<li>Rethink how you write CSS</li>
				</Transition>
				<Transition order={3}>
					<li>Or both</li>
				</Transition>
			</ol>
		</div>
	</Slide>

	<Slide class="Slide">
		<SVG class="h-auto w-full" icon="tailwind-v-css"></SVG>
	</Slide>

	<Slide class="Slide">
		<img alt="" src="/images/tailwind-girl.jpg" />
	</Slide>

	<Slide class="Slide">
		<img alt="" src="/images/css-girl.jpg" />
	</Slide>
	<!-- 
	<Slide class="Slide">
		<h1 class="HeroHeading text-center">Loyalty?</h1>
	</Slide> -->

	<Tools />

	<Slide class="Slide">
		<h1 class="text-center">Reinvent <br /> 🛞 the wheel 🛞</h1>
	</Slide>

	<Slide class="Slide">
		<blockquote class="SASuperhero">
			<p class="title">Make things better <br /> by making better things</p>
			<cite>Seth Godin</cite>
		</blockquote>
	</Slide>

	<Slide class="Slide">
		<img alt="" src="/images/caveman-2.png" />
	</Slide>

	<Slide class="Slide">
		<SVG class="mb-4 h-auto w-[18rem]" icon="tailwind"></SVG>
		<h1 class="text-cLightBlue-500">Tailwind</h1>
	</Slide>

	<TailwindIntro />

	<!-- Animation for the quotes would be nice -->
	<Slide class="Slide">
		<blockquote class="max-w-[45rem]">
			<p>
				I know what you’re thinking,
				<em class="text-cYellow-500">“this is an atrocity, what a horrible mess!”</em>
				and <span class="text-cTurquoise-500">you’re right, it’s kind of ugly</span>.
			</p>
			<cite>Adam Wathan</cite>
		</blockquote>
	</Slide>

	<Slide class="Slide">
		<blockquote class="max-w-[45rem]">
			<p>
				When you realize how productive you can be working exclusively in HTML with predefined
				utility classes, <span class="text-cYellow-500"
					>working any other way will feel like torture.</span
				>
			</p>
			<cite>Adam Wathan</cite>
		</blockquote>
	</Slide>

	<!-- See if can merge the two below into one animation . Then the circles in a continuous animation -->
	<Slide class="Slide gap-6">
		<h2>Laracon 2024 in Dallas</h2>
		<a href="https://youtu.be/MrzrSFbxW7M?si=aK5DLIh8JlHBfqpK&t=1018">
			<img alt="" src="/images/adam-laracon.png" />
		</a>
	</Slide>

	<Slide class="Slide gap-6">
		<h2>Laracon 2024 in Dallas</h2>
		<a href="https://youtu.be/MrzrSFbxW7M?si=aK5DLIh8JlHBfqpK&t=1018">
			<img alt="" src="/images/laracon-zoomed-in.png" />
		</a>
	</Slide>

	<Slide class="Slide gap-6">
		<h2>Laracon 2024 in Dallas</h2>
		<img alt="" src="/images/data-slot-icon.png" />
	</Slide>

	<Slide class="Slide gap-6">
		<h2>Laracon 2024 in Dallas</h2>
		<img alt="" src="/images/data-slot-control.png" />
	</Slide>

	<Slide class="Slide">
		<div
			class="title grid grid-cols-[auto_auto_auto] place-content-center place-items-center gap-16"
		>
			<div>✨</div>
			<div>✨</div>
			<div>✨</div>
			<div>✨</div>
			<h1 class="title text-cYellow-500 max-w-[45rem] text-center">Where Tailwind Shines</h1>
			<div>✨</div>
			<div>✨</div>
			<div>✨</div>
			<div>✨</div>
		</div>
	</Slide>

	<Slide class="Slide">
		<h1 class="title max-w-[14ch] text-center">Adjusting values on the fly</h1>
	</Slide>

	<AdjustValues />

	<Slide class="Slide gap-6">
		<h2>Tailwind Spacing Values</h2>
		<img alt="" src="/images/tailwind-spacing-1.png" />
	</Slide>

	<Slide class="Slide gap-6">
		<img alt="" src="/images/tailwind-spacing-2.png" />
	</Slide>

	<Slide class="Slide gap-6">
		<h2 class="Tailwind">Splendid Tailwind Layout Preset</h2>
		<table>
			<thead>
				<tr>
					<th>Unit</th>
					<th>Range</th>
					<th>Steps</th>
					<th>Example</th>
				</tr>
			</thead>
			<tbody>
				<tr>
					<td><code> - </code></td>
					<td><code>0 - 100 </code></td>
					<td><code>0.25 </code></td>
					<td><code>w-4</code></td>
				</tr>
				<tr>
					<td><code>rem</code></td>
					<td><code>0 - 100 </code></td>
					<td><code>0.25 </code></td>
					<td><code>w-4rem</code></td>
				</tr>
				<tr>
					<td><code>em</code></td>
					<td><code>0 - 100 </code></td>
					<td><code>0.25 </code></td>
					<td><code>w-4em</code></td>
				</tr>
				<tr>
					<td><code>ch</code></td>
					<td><code>0 - 100 </code></td>
					<td><code>0.25 </code></td>
					<td><code>w-4ch</code></td>
				</tr>
			</tbody>
		</table>
	</Slide>

	<Slide class="Slide">
		<img alt="" src="/images/splendidlabz-tailwind-layouts.png" />
	</Slide>

	<Slide class="Slide">
		<div class="Vertical">
			<h2>Install</h2>
			<div>
				<Code lang="shell" code={`npm install @splendidlabz/tailwind`}></Code>
			</div>

			<h2 class="mt-8">Usage</h2>
			<div>
				<Code
					lang="javascript"
					code={`
				import { layouts } from '@splendidlabz/tailwind/presets'

				export default {
					presets: [layouts]
				}`}
				></Code>
			</div>
		</div>
	</Slide>

	<Slide class="Slide">
		<h1 class="title max-w-[14ch] text-center">Responsive variants</h1>
	</Slide>

	<ResponsiveModifiers />

	<Slide class="Slide">
		<div>
			<table>
				<thead>
					<tr>
						<th>Symbol</th>
						<th>Breakpoint</th>
					</tr>
				</thead>
				<tbody>
					<tr>
						<td><code>sm</code></td>
						<td><code>640px</code></td>
					</tr>
					<tr>
						<td><code>md</code></td>
						<td><code>768px</code></td>
					</tr>
					<tr>
						<td><code>lg</code></td>
						<td><code>1024px</code></td>
					</tr>
					<tr>
						<td><code>xl</code></td>
						<td><code>1280px</code></td>
					</tr>
					<tr>
						<td><code>2xl</code></td>
						<td><code>1536px</code></td>
					</tr>
				</tbody>
			</table>
		</div>
	</Slide>

	<Slide class="Slide">
		<div class="GridRepeatAuto gap-24 [--cols:2]">
			<h2 class="Writing-rotateLeft text-center text-6xl">Media Breakpoints</h2>
			<table class="text-2xl">
				<thead>
					<tr>
						<th class="Tailwind">Symbol</th>
						<th class="Tailwind">Breakpoint</th>
					</tr>
				</thead>
				<tbody>
					<tr>
						<td><code>bp1</code></td>
						<td><code>100px</code></td>
					</tr>
					<tr>
						<td><code>bp1.5</code></td>
						<td><code>150px</code></td>
					</tr>
					<tr>
						<td><code>bp2</code></td>
						<td><code>200px</code></td>
					</tr>
					<tr>
						<td><code>bp2.5</code></td>
						<td><code>250px</code></td>
					</tr>
					<tr>
						<td><code>bp3</code></td>
						<td><code>300px</code></td>
					</tr>
					<tr>
						<td><code>bp3.5</code></td>
						<td><code>350px</code></td>
					</tr>
					<tr>
						<td><code>bp4</code></td>
						<td><code>400px</code></td>
					</tr>
					<tr>
						<td><code>bp4.5</code></td>
						<td><code>450px</code></td>
					</tr>
					<tr>
						<td><code>bp5</code></td>
						<td><code>500px</code></td>
					</tr>
					<tr>
						<td><code>...</code></td>
						<td><code>...</code></td>
					</tr>
					<tr>
						<td><code>bp19</code></td>
						<td><code>1900px</code></td>
					</tr>
					<tr>
						<td><code>bp19.5</code></td>
						<td><code>1950px</code></td>
					</tr>
					<tr>
						<td><code>bp20</code></td>
						<td><code>2000px</code></td>
					</tr>
				</tbody>
			</table>
		</div>
	</Slide>

	<Slide class="Slide">
		<div class="GridRepeatAuto gap-24 [--cols:2]">
			<h2 class="Writing-rotateLeft text-center text-6xl">Container Breakpoints</h2>
			<table class="text-2xl">
				<thead>
					<tr>
						<th class="Tailwind">Symbol</th>
						<th class="Tailwind">Breakpoint</th>
					</tr>
				</thead>
				<tbody>
					<tr>
						<td><code>@bp1</code></td>
						<td><code>100px</code></td>
					</tr>
					<tr>
						<td><code>@bp1.5</code></td>
						<td><code>150px</code></td>
					</tr>
					<tr>
						<td><code>@bp2</code></td>
						<td><code>200px</code></td>
					</tr>
					<tr>
						<td><code>@bp2.5</code></td>
						<td><code>250px</code></td>
					</tr>
					<tr>
						<td><code>@bp3</code></td>
						<td><code>300px</code></td>
					</tr>
					<tr>
						<td><code>@bp3.5</code></td>
						<td><code>350px</code></td>
					</tr>
					<tr>
						<td><code>@bp4</code></td>
						<td><code>400px</code></td>
					</tr>
					<tr>
						<td><code>@bp4.5</code></td>
						<td><code>450px</code></td>
					</tr>
					<tr>
						<td><code>@bp5</code></td>
						<td><code>500px</code></td>
					</tr>
					<tr>
						<td><code>...</code></td>
						<td><code>...</code></td>
					</tr>
					<tr>
						<td><code>@bp19</code></td>
						<td><code>1900px</code></td>
					</tr>
					<tr>
						<td><code>@bp19.5</code></td>
						<td><code>1950px</code></td>
					</tr>
					<tr>
						<td><code>@bp20</code></td>
						<td><code>2000px</code></td>
					</tr>
				</tbody>
			</table>
		</div>
	</Slide>

	<Slide class="Slide">
		<div
			class="title grid grid-cols-[auto_auto_auto] place-content-center place-items-center gap-16"
		>
			<div>🫥</div>
			<div>🫥</div>
			<div>🫥</div>
			<div>🫥</div>
			<h1 class="title text-cYellow-500 max-w-[45rem] text-center">Where Tailwind doesn't shine</h1>
			<div>🫥</div>
			<div>🫥</div>
			<div>🫥</div>
			<div>🫥</div>
		</div>
	</Slide>

	<Slide class="Slide">
		<div class="title">Repeating Variants</div>
	</Slide>

	<Slide class="Slide gap-6">
		<img alt="" src="/images/data-slot-icon.png" />
	</Slide>

	<Slide class="Slide">
		<div class="Vertical gap-6">
			<h2>HTML</h2>
			<div>
				<Code
					lang="html"
					code={`<button class="bg-blue-500 text-gray-800 
					  hover:bg-blue-600 hover:text-gray-900 
						focus:bg-blue-600 focus:text-gray-900
					"> ... </button>`}
				></Code>
			</div>
			<button
				class="bg-blue-500 text-gray-800 hover:bg-blue-600 hover:text-gray-900 focus:bg-blue-600 focus:text-gray-900"
			>
				Click me
			</button>
		</div>
	</Slide>

	<Slide class="Slide">
		<div class="Vertical gap-6">
			<h2 class="text-center">Better to use CSS</h2>
			<div>
				<Code
					lang="scss"
					code={`.Component {
					  background: var(--blue-500);
						color: var(--gray-900);

						&:hover, 
						&:focus {
						  background: var(--blue-600);
							color: var(--gray-900);
						}
					}`}
				></Code>
			</div>
		</div>
	</Slide>

	<Slide class="Slide">
		<div class="title">Pseudo Elements</div>
	</Slide>

	<PseudoElements />

	<Slide class="Slide">
		<div class="grid grid-cols-[auto_auto_auto] place-content-center place-items-center gap-16">
			<div class="SASuperhero text-cPink-500 -rotate-30">Deal</div>
			<div class="SASuperhero text-cPink-500 rotate-0">Deal</div>
			<div class="SASuperhero text-cPink-500 rotate-30">Deal</div>
			<div class="SASuperhero text-cPink-500 -rotate-90">Deal</div>
			<h1 class="title text-cYellow-500 max-w-[45rem] text-center">What sealed the deal</h1>
			<div class="SASuperhero text-cPink-500 rotate-90">Deal</div>
			<div class="SASuperhero text-cPink-500 rotate-210">Deal</div>
			<div class="SASuperhero text-cPink-500 rotate-180">Deal</div>
			<div class="SASuperhero text-cPink-500 rotate-150">Deal</div>
		</div>
	</Slide>

	<Slide class="Slide">
		<h1 class="HeroHeading title">
			<span class="Eyebrow">💋</span>
			<span>Arbitrary properties</span>
		</h1>
	</Slide>

	<Slide class="Slide">
		<div>
			<Code
				lang="html"
				codes={[
					`<div class="[property:value]">
						... 
					</div>`,
					`<div class="[--css-variable:value]">
						...
					</div>`,
					`<div class="bp5:[--css-variable:value]">
						...
					</div>`
				]}
			></Code>
		</div>
	</Slide>

	<Slide class="Slide">
		<h1 class="title">
			💋
			<span>@Apply</span>
		</h1>
	</Slide>

	<Slide class="Slide">
		<div>
			<Code
				lang="css"
				code={`.selector { @apply component; }
			.selector { @apply utility; }`}
			></Code>
		</div>
	</Slide>

	<!-- END TAILWIND PROS CONS -->

	<Slide class="Slide">
		<h1 class="HeroHeading gap-0 text-center">
			<span class="CSS">CSS</span>
			<span>&</span>
			<span class="Tailwind">Tailwind</span>
		</h1>
	</Slide>

	<Slide class="Slide">
		<h1 class="title Horizontal">
			<span class="-rotate-30">❤️</span>
			<div>
				<span class="Tailwind">Sys</span><span class="CSS">tem</span>
			</div>
			<span class="rotate-30">❤️</span>
		</h1>
	</Slide>

	<CreateCompsLogic />

	<Slide class="Slide">
		<h1 class="title">Creating components</h1>
	</Slide>

	<Slide class="Slide">
		<div>
			<Code
				lang="css"
				codes={[
					`@layer components {
						.Component {
							/* ... Your styles here ... */
						}
					}`
				]}
			></Code>
		</div>
	</Slide>

	<CreateCompsHorizontalAndVertical />
	<CreateCompsGrid />
	<CreateCompsInlineStyle />

	<Slide class="Slide">
		<h1 class="title">Back to Simple Grid</h1>
	</Slide>

	<CreateCompsGrid2 />

	<Slide class="Slide">
		<h1 class="title">No Need Tailwind</h1>
	</Slide>

	<Slide class="Slide">
		<div class="SimpleGrid [--cols:2]">
			<div class="Vertical">
				<h2>HTML</h2>
				<div>
					<Code lang="html" code={`<div class="SimpleGrid YourGrid"> ... </div>`} />
				</div>
			</div>

			<div class="Vertical">
				<h2>CSS</h2>
				<div>
					<Code
						lang="css"
						code={`
					.YourGrid {
						--cols: 2;
						
						@media (width >= 800px) {
							--cols: 3
						}
					}`}
					/>
				</div>
			</div>
		</div>
	</Slide>

	<Slide class="Slide">
		<h1 class="title">@apply</h1>
	</Slide>

	<Slide class="Slide">
		<div class="SimpleGrid [--cols:2]">
			<div class="Vertical">
				<h2>HTML</h2>
				<div>
					<Code
						lang="html"
						codes={[
							`<div class="SimpleGrid YourGrid"> ... </div>`,
							`<div class="YourGrid"> ... </div>`
						]}
					/>
				</div>
			</div>

			<div class="Vertical">
				<h2>CSS</h2>
				<div>
					<Code
						lang="css"
						codes={[
							`
					.YourGrid {
						--cols: 2;
						
						@media (width >= 800px) {
							--cols: 3
						}
					}`,
							`
					.YourGrid {
					  @apply SimpleGrid;
						--cols: 2;
						
						@media (width >= 800px) {
							--cols: 3
						}
					}`,
							`
					.YourGrid {
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
							
						--cols: 2;

						@media (width >= 800px) {
							--cols: 3
						}
					}`
						]}
					/>
				</div>
			</div>
		</div>
	</Slide>

	<Slide class="Slide">
		<h1 class="title">Logic</h1>
	</Slide>

	<CreateCompsLogic />

	<Slide class="Slide">
		<h1 class="title">More examples</h1>
	</Slide>

	<More />

	<Slide class="Slide">
		<h1 class="Tailwind">Colours</h1>
	</Slide>

	<Slide class="Slide">
		<img src="/images/tw-colors.png" />
	</Slide>

	<Slide class="Slide">
		<div>
			<table class="text-left">
				<thead>
					<tr>
						<th>Property</th>
						<th>Keyword</th>
					</tr>
				</thead>
				<tbody>
					<tr>
						<td>background</td>
						<td><code>bg-*</code></td>
					</tr>
					<tr>
						<td>color</td>
						<td><code>text-*</code></td>
					</tr>
					<tr>
						<td>border-color</td>
						<td><code>border-*</code></td>
					</tr>
				</tbody>
			</table>
		</div>
	</Slide>

	<ColorIntro />
	<ColorPreset />
	<DynamicColors />

	<Slide class="Slide">
		<h1 class="title">Fill System</h1>
	</Slide>

	<Slide class="Slide">
		<div class="Vertical gap-6">
			<h2>HTML</h2>
			<div>
				<Code
					lang="html"
					code={`<button class="bg-blue-500 text-gray-800 
					  hover:bg-blue-600 hover:text-gray-900 
						focus:bg-blue-600 focus:text-gray-900
					"> ... </button>`}
				></Code>
			</div>
			<button
				class="bg-blue-500 text-gray-800 hover:bg-blue-600 hover:text-gray-800 focus:bg-blue-600 focus:text-gray-800"
			>
				Click me
			</button>
		</div>
	</Slide>

	<FillSystem />
	<FillPlugin />
	<ColorPreset />

	<Slide class="Slide">
		<h1>Typography</h1>
	</Slide>

	<ChooseFontSize />
	<FluidVsResponsive />

	<TypeTailwind />
	<TypeTailwind2 />

	<ResponsiveType />
	<ResponsiveType2 />

	<Slide class="Slide">
		<h1 class="title">@apply</h1>
	</Slide>

	<Slide class="Slide">
		<div class="Vertical gap-6">
			<div class="min-w-[500px]">
				<Code
					lang="css"
					codes={[
						`.selector {
					  
					}`,
						`.selector {
					  @apply Marvin; 
					}`,
						`.selector {
					  @apply Marvin Marvin-base; 
					}`,
						`.selector {
					  @apply Marvin Marvin-base Marvin-1; 
					}`
					]}
				></Code>
			</div>
		</div>
	</Slide>

	<Slide class="Slide">
		<h1>Wrapping Up</h1>
	</Slide>

	<Slide class="Slide">
		<div class="Flow gap-16">
			<Transition order={1} class="title">Tools</Transition>
			<Transition order={2} class="title Tailwind">✨</Transition>
			<Transition order={3} class="title Tailwind">🫥</Transition>
			<Transition order={4}>
				<div class="!SASuperhero text-cPink-500 text-8xl">Deal</div>
			</Transition>
		</div>
	</Slide>

	<Slide class="Slide">
		<div class="Vertical items-center">
			<Transition order={1}>
				<h1 class="title Horizontal">
					<span class="-rotate-30">❤️</span>
					<div>
						<span class="Tailwind">Sys</span><span class="CSS">tem</span>
					</div>
					<span class="rotate-30">❤️</span>
				</h1>
			</Transition>
			<div class="Flow gap-16">
				<Transition order={2} class="title">Layouts</Transition>
				<Transition order={3} class="title Tailwind">Colours</Transition>
				<Transition order={4} class="title !text-cTurquoise-500">Typography</Transition>
			</div>
		</div>
	</Slide>

	<Slide class="Slide">
		<div class="SASuperhero">
			<p>Hopefully this has caused you to:</p>
			<ol>
				<Transition order={1}>
					<li>Rethink how you use Tailwind</li>
				</Transition>
				<Transition order={1}>
					<li>Rethink how you write CSS</li>
				</Transition>
				<Transition order={1}>
					<li>Or both</li>
				</Transition>
				<Transition order={2}>
					<li>Rethink your systems</li>
				</Transition>
			</ol>
		</div>
	</Slide>

	<Slide class="Slide">
		<h1>
			More <span class="text-cTurquoise-500">Fun</span> <br /> Less
			<span class="text-cPink-500">Pain</span>
		</h1>
	</Slide>

	<Slide class="Slide">
		<div class="Vertical">
			<div class="Stack">
				<h1>Thank you</h1>
				<div
					class="Marvin-light SASuperhero GridRepeatAuto Edge-bottomfull top-[4rem] items-center gap-2 [--cols:2]"
				>
					<div class="Horizontal items-center">
						<SVG icon="pepicons-pop:internet" />
						<a href="https://splendidlabz.com" target="_blank">https://splendidlabz.com</a>
					</div>

					<div class="Horizontal items-center">
						<SVG icon="logos:twitter" />
						<a href="https://x.com/zellwk" target="_blank">@zellwk</a>
					</div>

					<div class="Horizontal items-center">
						<SVG icon="pepicons-pop:internet" />
						<a href="https://zellwk.com" target="_blank">https://zellwk.com</a>
					</div>

					<div class="Horizontal items-center">
						<SVG icon="twemoji:butterfly" />
						<a href="https://x.com/zellwk" target="_blank">@zellwk.bsky.social</a>
					</div>
				</div>
			</div>
		</div>
	</Slide>
</Presentation>
