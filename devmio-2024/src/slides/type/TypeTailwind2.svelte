<script lang="ts">
	import { Action, Code, Slide } from '@animotion/core'

	let codeHTML: ReturnType<typeof Code>
	let codeCSS: ReturnType<typeof Code>
	let codeCSS2: ReturnType<typeof Code>
	let codeJS: ReturnType<typeof Code>
	let codeJS2: ReturnType<typeof Code>
	let example: HTMLDivElement
</script>

<Slide class="Slide">
	<div class="GridRepeatAuto [--cols:2]">
		<div class="Vertical">
			<div>
				<Code
					bind:this={codeJS}
					lang="js"
					code={`export default {
  theme: {
    fontSize: {
      'Marvin-1': ['16px', {
        lineHeight: '2rem',
        letterSpacing: '-0.01em',
        fontWeight: '500',
      }],
    }
  }
}`}
				></Code>
			</div>
		</div>
	</div>
</Slide>

<Slide class="Slide">
	<h1 class="title">
		<span class="text-cPink-500">Adobe</span>
		<span>&</span>
		<span class="text-cTurquoise-500">Variable Fonts</span>
	</h1>
</Slide>

<Slide class="Slide">
	<a href="https://v-fonts.com/fonts/roboto-flex" target="_blank">
		<img src="/images/variation.png" alt="" />
	</a>
</Slide>

<Slide class="Slide">
	<div class="GridRepeatAuto gap-x-12 gap-y-8 [--cols:2]">
		<h2 class="text-center">Normal V-fonts</h2>
		<h2 class="text-center">Adobe V-fonts</h2>

		<div>
			<Code
				lang="css"
				codes={[
					``,
					`.Marvin {
  font-weight: 400;
  font-optical-sizing: 80;
}`
				]}
			/>
		</div>
		<div>
			<Code
				lang="css"
				codes={[
					``,
					`.Marvin {
  font-variations-settings: 'wght' 400, 'opsz' 80;
}`,
					`.Marvin {
  font-variations-settings: 
    'wght' var(--font-weight, 400),
    'opsz' var(--font-optical-sizing, 80);
}`
				]}
			/>
		</div>
	</div>
</Slide>

<Slide class="Slide">
	<div class="GridRepeatAuto [--cols:2]">
		<div>
			<Code
				bind:this={codeJS2}
				lang="js"
				code={`export default {
  theme: {
    fontSize: {
      'Marvin-1': ['16px', {
        lineHeight: '2rem',
        letterSpacing: '-0.01em',
        fontWeight: '500',
      }],
    }
  }
}`}
			></Code>
		</div>

		<div>
			<Code bind:this={codeCSS2} lang="css" code={``}></Code>
		</div>
	</div>

	<Action
		actions={[
			async () => {
				await codeJS2.update`export default {
  theme: {
    splendidType: {
      // ...
    }
  }
}`
				await codeJS2.selectLines`3-5`
			},
			async () => {
				await codeJS2.update`export default {
  theme: {
    splendidType: {
      Marvin: {
        // ...
      }
    }
  }
}`
				await codeJS2.selectLines`4-6`
			},

			,
			async () => {
				await codeJS2.update`export default {
  theme: {
    splendidType: {
      Marvin: {
        1: {
          // ...
        }
      }
    }
  }
}`
				await codeJS2.selectLines`5-7`
			},

			async () => {
				await codeCSS2.update`.Marvin-1 {
  /* ... */
}`
			},
			async () => {
				await codeJS2.update`export default {
  theme: {
    splendidType: {
      Marvin: {
        1: {
          size: '16px',
          leading: 1.5,
          // Other CSS Properties
        }
      }
    }
  }
}`
			},
			async () => {
				await codeCSS2.update`.Marvin-1 {
  font-size: '16px',
  line-Height: 1.5,
}`
				await codeJS2.selectLines`5-9`
			},
			async () => {
				await codeJS2.update`export default {
  theme: {
    splendidType: {
      Marvin: {
        1: {
          size: '16px',
          leading: 1.5,
          fontVariationSettings: \`
            'wght' var(--font-weight), 
            'opsz' var(--font-optical-sizing)\`
        }
      }
    }
  }
}`
				await codeJS2.selectLines`8-10`
			},
			async () => {
				await codeCSS2.update`.Marvin-1 {
  font-size: '16px',
  line-height: 1.5,
  font-variations-settings: 
    'wght' var(--font-weight), 
    'opsz' var(--font-optical-sizing),
}`
				await codeCSS2.selectLines`4-6`
			},
			async () => {
				await codeJS2.update`export default {
  theme: {
    splendidType: {
      Marvin: {
        1: {
          size: '16px',
          leading: 1.5,
          fontVariationSettings: \`
            'wght' var(--font-weight), 
            'opsz' var(--font-optical-sizing)\`,
          '--font-weight': '400',
          '--font-optical-sizing': '80',
        }
      }
    }
  }
}`
				await codeJS2.selectLines`8-12`
			},
			async () => {
				await codeCSS2.update`.Marvin-1 {
  --font-weight: 400;
  --font-optical-sizing: 80;
  font-size: '16px',
  line-height: 1.5,
  font-variations-settings: 
    'wght' var(--font-weight), 
    'opsz' var(--font-optical-sizing),
}`
				await codeCSS2.selectLines`2,3,6-8`
			},
			async () => {
				await codeJS2.update`import { fontVariationSettings } from '@splendidlabz/tailwind/utils'
        
export default {
  theme: {
    splendidType: {
      Marvin: {
        1: {
          size: '16px',
          leading: 1.5,
          fontVariationSettings: fontVariationSettings({
            opticalSize: 80,
            weight: 400 
          }),
          '--font-weight': '400',
          '--font-optical-sizing': '80',
        }
      }
    }
  }
}`
				await codeJS2.selectLines`1,10-13`
			},

			async () => {
				await codeCSS2.update`.Marvin-1 {
  --font-weight: 400;
  --font-optical-sizing: 80;
  font-size: '16px',
  line-height: 1.5,
  font-variations-settings: 
    'wght' var(--font-weight, 400), 
    'opsz' var(--font-optical-sizing, 80),
}`
				await codeCSS2.selectLines`7-8`
			},

			async () => {
				await codeJS2.update`import { fontVariationSettings } from '@splendidlabz/tailwind/utils'
        
export default {
  theme: {
    splendidType: {
      Marvin: {
        base: {
          size: '16px',
          leading: 1.5,
          fontVariationSettings: fontVariationSettings({
            opticalSize: 80,
            weight: 400 
          }),
        }, 
        1: {
          size: '18px',
          '--font-weight': '600',
          '--font-optical-sizing': '90',
        }
      }
    }
  }
}`
				await codeJS2.selectLines`7, 10-14`
			},

			async () => {
				await codeJS2.selectLines`15, 17-19`
			},

			async () => {
				await codeCSS2.update`[class*="Marvin"] {
  font-size: '16px',
  line-height: 1.5,
  font-variations-settings: 
    'wght' var(--font-weight, 400), 
    'opsz' var(--font-optical-sizing, 80),
}

.Marvin-1 {
  font-size: 18px;
  --font-weight: 600;
  --font-optical-sizing: 90;
}    `
				await codeCSS2.selectLines`1, 4-6`
			},

			async () => {
				await codeCSS2.selectLines`8-13`
			},

			async () => {
				await codeJS2.update`export default {
  theme: {
    splendidType: {
      Marvin: {
        // ... 
        2: '18px',
        3: ['24px', 1.2],
      }
    }
  }
}`
				await codeJS2.selectLines`6-7`
			},

			async () => {
				await codeCSS2.update`[class*="Marvin"] {
  font-size: '16px',
  line-height: 1.5,
  font-variations-settings: 
    'wght' var(--font-weight, 400), 
    'opsz' var(--font-optical-sizing, 80),
}

.Marvin-1 { /* ... */ }
.Marvin-2 { /* ... */ }
.Marvin-3 { /* ... */ }`
				await codeCSS2.selectLines`10-11`
			}
		]}
	/>
</Slide>
