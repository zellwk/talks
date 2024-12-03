<script lang="ts">
	import { Code, Slide, Transition } from '@animotion/core'
	import TypePreset from './TypePreset.svelte'

	let codeHTML: ReturnType<typeof Code>
	let codeCSS: ReturnType<typeof Code>
	let codeJS: ReturnType<typeof Code>
	let code2: ReturnType<typeof Code>

	let marvin: HTMLDivElement
	let jetbrains: HTMLDivElement
	let modularScale: HTMLHeadingElement
	let typographyScale: HTMLHeadingElement

	let mstsItems = $state([1, 2, 3])
</script>

<Slide class="Slide">
	<img class="h-[520px] w-[1000px]" src="/images/tw-font-size.png" alt="" />
</Slide>

<Slide class="Slide">
	<table class="w-full text-2xl">
		<thead>
			<tr>
				<th class="text-left">Class</th>
				<th class="text-left">Font Size</th>
				<th class="text-left">Line Height</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td><code>text-xs</code></td>
				<td><code>12px</code></td>
				<td><code>16px</code></td>
			</tr>
			<tr>
				<td><code>text-sm</code></td>
				<td><code>14px</code></td>
				<td><code>20px</code></td>
			</tr>
			<tr>
				<td><code>text-base</code></td>
				<td><code>16px</code></td>
				<td><code>24px</code></td>
			</tr>
			<tr>
				<td><code>text-lg</code></td>
				<td><code>18px</code></td>
				<td><code>28px</code></td>
			</tr>
			<tr>
				<td><code>text-xl</code></td>
				<td><code>20px</code></td>
				<td><code>28px</code></td>
			</tr>
			<tr>
				<td><code>text-2xl</code></td>
				<td><code>24px</code></td>
				<td><code>32px</code></td>
			</tr>
			<tr>
				<td><code>text-3xl</code></td>
				<td><code>30px</code></td>
				<td><code>36px</code></td>
			</tr>
			<tr>
				<td><code>text-4xl</code></td>
				<td><code>36px</code></td>
				<td><code>40px</code></td>
			</tr>
			<tr>
				<td><code>text-5xl</code></td>
				<td><code>48px</code></td>
				<td><code>1</code></td>
			</tr>
			<tr>
				<td><code>text-6xl</code></td>
				<td><code>60px</code></td>
				<td><code>1</code></td>
			</tr>
			<tr>
				<td><code>text-7xl</code></td>
				<td><code>72px</code></td>
				<td><code>1</code></td>
			</tr>
			<tr>
				<td><code>text-8xl</code></td>
				<td><code>96px</code></td>
				<td><code>1</code></td>
			</tr>
			<tr>
				<td><code>text-9xl</code></td>
				<td><code>128px</code></td>
				<td><code>1</code></td>
			</tr>
		</tbody>
	</table>
</Slide>

<Slide class="Slide">
	<div>
		<Code
			lang="js"
			code={`module.exports = {
				theme: {
					fontSize: {
						xs: ['12px', '16px'],
						sm: ['14px', '20px'],
						base: ['16px', '24px'],
						lg: ['18px', '28px'],
						xl: ['20px', '28px'],
						'2xl': ['24px', '32px'],
						'3xl': ['30px', '36px'],
						'4xl': ['36px', '40px'],
						'5xl': ['48px', '1'],
						'6xl': ['60px', '1'],
						'7xl': ['72px', '1'],
						'8xl': ['96px', '1'],
						'9xl': ['128px', '1']
					}
				}
			}`}
		></Code>
	</div>
</Slide>

<!-- 
<Slide class="Slide">
	<div class="Horizontal gap-8 text-8xl">
		<Transition>
			<div bind:this={marvin} class="Marvin BigText text-cPink-500">Marvin Visions</div>
		</Transition>
		<Transition>
			<div bind:this={jetbrains} class="Jetbrains BigText text-cYellow-500">Jetbrains Mono</div>
		</Transition>
	</div>

	<Transition
		do={async () => {
			marvin.style.opacity = '0.5'
			jetbrains.style.opacity = '0.5'
		}}
	/>

	<Transition
		do={async () => {
			marvin.style.transform = 'translateX(50%)'
		}}
	/>
	<Transition
		do={async () => {
			jetbrains.style.opacity = '0.5'
			marvin.style.transform = 'translateX(50%)'
			jetbrains.style.transform = 'translateX(-50%)'
		}}
	/>
</Slide> -->

<Slide class="Slide">
	<h1 class="title text-center">choosing <br /> font sizes</h1>
</Slide>

<Slide class="Slide">
	<div class="SimpleGrid [--cols:2]">
		<h2 class="text-cPink-500">Modular Scale</h2>
		<h2 class="text-cTurquoise-500">Typography Scale</h2>
	</div>
</Slide>

<Slide class="Slide">
	<div class="Vertical">
		<h2 class="text-cPink-500">Modular Scale</h2>
		<img src="/images/modular-scale-2.png" alt="" />
	</div>
</Slide>

<Slide class="Slide">
	<div class="Vertical">
		<h2 class="text-cPink-500">Modular Scale</h2>
		<img src="/images/modular-scale.png" alt="" />
	</div>
</Slide>

<Slide class="Slide">
	<div class="Vertical">
		<h2>Install</h2>
		<div>
			<Code lang="shell" code={`npm install --save-dev tailwindcss-modularscale`}></Code>
		</div>

		<h2 class="mt-8">Usage</h2>
		<div>
			<Code
				lang="js"
				codes={[
					`module.exports = {
  // ...
  plugins: [
    require('tailwindcss-modularscale')()
  ],
				}`,
					`module.exports = {
  // ...
  plugins: [
		require('tailwindcss-modularscale')({
			sizes: [
				{ size: 'sm', value: -1 },
				{ size: 'base', value: 0 },
				{ size: 'lg', value: 1 },
				{ size: 'xl', value: 2 },
				{ size: '2xl', value: 3 },
				{ size: '3xl', value: 4 },
				{ size: '4xl', value: 5 }
			],
			base:  16,
			ratio: 1.333, // Perfect Fourth
			unit: 'px',
		})
	],
}`
				]}
			></Code>
		</div>
	</div>
</Slide>

<Slide class="Slide">
	<div class="Vertical">
		<h2 class="text-cTurquoise-500">Typography Scale</h2>
		<img class="h-[520px] w-[1000px]" src="/images/typography-scale.jpg" alt="" />
	</div>
</Slide>

<Slide class="Slide">
	<div class="SimpleGrid [--cols:2]">
		<table class="text-3xl">
			<thead>
				<tr>
					<th>Step</th>
					<th>Size</th>
				</tr>
			</thead>
			<tbody>
				<tr>
					<td><code>1</code></td>
					<td><code>10px</code></td>
				</tr>
				<tr>
					<td>2</td>
					<td><code>11px</code></td>
				</tr>
				<tr>
					<td>3</td>
					<td><code>12px</code></td>
				</tr>
				<tr>
					<td>4</td>
					<td><code>13px</code></td>
				</tr>
				<tr>
					<td>5</td>
					<td><code>14px</code></td>
				</tr>
				<tr>
					<td>6</td>
					<td><code>15px</code></td>
				</tr>
				<tr>
					<td>7</td>
					<td><code>16px</code></td>
				</tr>
				<tr>
					<td>8</td>
					<td><code>18px</code></td>
				</tr>
				<tr>
					<td>9</td>
					<td><code>21px</code></td>
				</tr>
				<tr>
					<td>10</td>
					<td><code>24px</code></td>
				</tr>
				<tr>
					<td>11</td>
					<td><code>28px</code></td>
				</tr>
			</tbody>
		</table>
		<table class="text-3xl">
			<thead>
				<tr>
					<th>Step</th>
					<th>Size</th>
				</tr>
			</thead>
			<tbody>
				<tr>
					<td>12</td>
					<td><code>32px</code></td>
				</tr>
				<tr>
					<td>13</td>
					<td><code>36px</code></td>
				</tr>
				<tr>
					<td>14</td>
					<td><code>42px</code></td>
				</tr>
				<tr>
					<td>15</td>
					<td><code>48px</code></td>
				</tr>
				<tr>
					<td>16</td>
					<td><code>54px</code></td>
				</tr>
				<tr>
					<td>17</td>
					<td><code>60px</code></td>
				</tr>
				<tr>
					<td>18</td>
					<td><code>72px</code></td>
				</tr>
				<tr>
					<td>19</td>
					<td><code>84px</code></td>
				</tr>
				<tr>
					<td>20</td>
					<td><code>96px</code></td>
				</tr>
				<tr>
					<td>21</td>
					<td><code>108px</code></td>
				</tr>
				<tr>
					<td>22</td>
					<td><code>120px</code></td>
				</tr>
			</tbody>
		</table>
	</div>
</Slide>

<Slide class="Slide">
	<div class="w-[30ch]">
		<Code
			lang="js"
			code={`module.exports = {
	theme: {
		extend {
			fontSize: {
				1: '10px',
				2: '11px',
				3: '12px',
				// ...
				7: '16px',
				'8': '18px',
				'9': '21px',
				// ... 
				22: '120px',
			}
		}
	}
}`}
		></Code>
	</div>
</Slide>

<TypePreset />

<Slide class="Slide">
	<Transition>
		<div class="Horizontal items-center gap-8 text-8xl">
			{#each mstsItems as item, i (item)}
				<div
					class="BigText text-cPink-500 Marvin text-center"
					class:text-cPink-500={item === 1}
					class:text-cYellow-500={item === 2}
					class:text-cTurquoise-500={item === 3}
				>
					{#if item === 1}Modular Scale{/if}
					{#if item === 2}VS{/if}
					{#if item === 3}Typography Scale{/if}
				</div>
			{/each}
		</div>
	</Transition>

	<Transition do={() => (mstsItems = [3])} />
</Slide>
