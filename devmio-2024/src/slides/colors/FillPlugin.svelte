<script lang="ts">
	import { Action, Code, Slide } from '@animotion/core'

	let codeCSS: ReturnType<typeof Code>
	let codeConfig: ReturnType<typeof Code>
	let code2: ReturnType<typeof Code>
	let item: HTMLDivElement
</script>

<Slide class="Slide">
	<div class="Vertical">
		<h2 class="text-center">Fill Plugin</h2>
		<div class="GridRepeatAuto [--cols:2]">
			<div>
				<Code
					bind:this={codeCSS}
					lang="javascript"
					code={`.Fill-blue-outline {
  --text-color: var(--blue-500);
  --border-color: var(--blue-500);
  --text-hover-color: var(--blue-600);
  --border-hover-color: var(--blue-600);
}
          
.Fill-blue-light {
  --bg-color: var(--blue-900);
  --text-color: var(--gray-200);
  --border-color: var(--blue-500);
  --bg-hover-color: var(--blue-800);
}

.Fill-blue-heavy {
  --bg-color: var(--blue-500);
  --text-color: var(--gray-800);
  --bg-hover-color: var(--blue-600);
}`}
				/>
			</div>
			<div class="text-4xl">
				<Code bind:this={codeConfig} lang="javascript" code={``} />
			</div>
		</div>
	</div>

	<Action
		do={async () => {
			await codeConfig.update`export default {
  theme: {
    splendidFills: {
      // ...
    }
  }
}`
			await codeConfig.selectLines`3-5`
		}}
	/>

	<Action
		do={async () => {
			await codeConfig.update`export default {
  theme: {
    splendidFills: {
      blue: {
        outline: {},
        light: {},
        heavy: {}
      }
    }
  }
}`
			await codeConfig.selectLines`4-8`
			await codeCSS.selectLines`1,8,15`
		}}
	/>

	<Action
		do={async () => {
			await codeConfig.update`export default {
  theme: {
    splendidFills: {
      blue: {
        outline: {
          text: 'blue.500',
          border: 'blue.500',
          textHover: 'blue.600',
          borderHover: 'blue.600'
        },
        light: {},
        heavy: {}
      }
    }
  }
}`

			await codeCSS.update`.Fill-blue-light {
  --bg-color: var(--blue-900);
  --text-color: var(--gray-200);
  --border-color: var(--blue-500);
  --bg-hover-color: var(--blue-800);
}

.Fill-blue-heavy {
  --bg-color: var(--blue-500);
  --text-color: var(--gray-800);
  --bg-hover-color: var(--blue-600);
}`
			await codeConfig.selectLines`5-10`
		}}
	/>

	<Action
		do={async () => {
			await codeConfig.update`export default {
  theme: {
    splendidFills: {
      blue: {
        outline: {
          text: 'blue.500',
          border: 'blue.500',
          textHover: 'blue.600',
          borderHover: 'blue.600'
        },
        light: {
          bg: 'blue.900',
          text: 'gray.200',
          border: 'blue.500',
          bgHover: 'blue.800'
        },
        heavy: {}
      }
    }
  }
}`

			await codeCSS.update`.Fill-blue-heavy {
  --bg-color: var(--blue-500);
  --text-color: var(--gray-800);
  --bg-hover-color: var(--blue-600);
}`
			await codeConfig.selectLines`11-16`
		}}
	/>

	<Action
		do={async () => {
			await codeConfig.update`export default {
  theme: {
    splendidFills: {
      blue: {
        outline: {
          text: 'blue.500',
          border: 'blue.500',
          textHover: 'blue.600',
          borderHover: 'blue.600'
        },
        light: {
          bg: 'blue.900',
          text: 'gray.200',
          border: 'blue.500',
          bgHover: 'blue.800'
        },
        heavy: {
          bg: 'blue.500',
          text: 'gray.800',
          bgHover: 'blue.600'
        }
      }
    }
  }
}`

			await codeCSS.update``
			await codeConfig.selectLines`17-21`
		}}
	/>
</Slide>

<Slide class="Slide">
	<div class="GridRepeatAuto gap-6 [--cols:2]">
		<div class="text-4xl">
			<Code
				lang="javascript"
				code={`export default {
  theme: {
    splendidFills: {
      blue: {
        outline: {
          text: 'blue.500',
          border: 'blue.500',
          textHover: 'blue.600',
          borderHover: 'blue.600'
        },
        light: {
          bg: 'blue.900',
          text: 'gray.200',
          border: 'blue.500',
          bgHover: 'blue.800'
        },
        heavy: {
          bg: 'blue.500',
          text: 'gray.800',
          bgHover: 'blue.600'
        }
      }
    }
  }
}`}
			></Code>
		</div>

		<div class="Vertical justify-around">
			<button class="Fill-blue-outline self-center"> Outline </button>
			<button class="Fill-blue-light self-center"> Light </button>
			<button class="Fill-blue self-center"> Heavy </button>
		</div>
	</div>
</Slide>
