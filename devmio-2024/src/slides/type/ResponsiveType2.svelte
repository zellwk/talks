<script lang="ts">
	import { Action, Code, Slide } from '@animotion/core'

	let codeJS: ReturnType<typeof Code>
	let codeJS2: ReturnType<typeof Code>
	let codeCSS: ReturnType<typeof Code>
</script>

<Slide class="Slide">
	<div class="GridRepeatAuto [--cols:3]">
		<div>
			<Code
				bind:this={codeJS}
				lang="js"
				code={`splendidType: {
  Marvin: {
    base: {
      size: '16px', 
      leading: 1.5,
      fontVariationSettings: /* ... */
    },
    1: {
      size: '18px'
      --font-weight: '600', 
      --font-optical-sizing: '90'
    }
    2: '21px',
    3: '24px',
  }
}`}
			/>
		</div>
		<div>
			<Code bind:this={codeJS2} lang="js" code={``} />
		</div>

		<div>
			<Code bind:this={codeCSS} lang="css" code={``} />
		</div>

		<Action
			actions={[
				async () => {
					await codeJS2.update`splendidResponsiveType: {
  Marvin: {
    '1R': {
      base: '.Marvin-1'
    }
  }
}`
				},

				async () => {
					await codeJS2.selectLines`4`
					await codeJS.selectLines`8-12`
				},

				async () => {
					await codeCSS.update`.Marvin-1R {
  --font-weight: 600; 
  --font-optical-sizing: 90;
  font-size: 18px;
}
  `
				},

				async () => {
					await codeJS2.update`splendidResponsiveType: {
  Marvin: {
    '1R': {
      base: '.Marvin-1',
      bp6: '.Marvin-2',
      bp9: '.Marvin-3',
    }
  }
}`

					await codeJS2.selectLines`4-6`
				},

				async () => {
					await codeJS.selectLines`8-14`
				},

				async () => {
					await codeCSS.update`.Marvin-1R {
  --font-weight: 600;
  --font-optical-sizing: 90;
  font-size: 18px;

  @media (width >= 600px) {
    font-size: 21px;
  }

  @media (width >= 900px) {
    font-size: 24px;
  }
}`
				},

				async () => {
					await codeJS2.update`splendidResponsiveType: {
  Marvin: {
    '1R': {
      base: '.Marvin-1',
      bp6: '.Marvin-2',
      bp9: '.Marvin-3',
      bp10: ['30px', 1.5]
    }
  }
}`

					await codeJS2.selectLines`7`
					await codeJS.selectLines`0`
				},

				async () => {
					await codeCSS.update`.Marvin-1R {
  /* ... */
  @media (width >= 1000px) {
    font-size: 30px;
    line-height: 1.5;
  }
}`
				},

				async () => {
					await codeJS.update`splendidType: {
  Marvin: {
    base: /* ... */, 
    1: /* ... */,
    2: /* ... */,
    3: /* ... */,
  }
}`
					await codeJS.selectLines`3-6`
				},

				async () => {
					await codeCSS.update`[class*='Marvin'] { /* Base */ }
          
.Marvin-1 { /* 1 */ }
.Marvin-2 { /* 2 */ }
.Marvin-3 { /* 3 */ }`
				},

				async () => {
					await codeJS2.update`splendidResponsiveType: {
  Marvin: {
    '1R': /* ... */,
    '2R': /* ... */,
    '3R': /* ... */,
    '4R': /* ... */,
  }
}`

					await codeJS2.selectLines`3-6`
				},

				async () => {
					await codeCSS.update`[class*='Marvin'] { /* Base */ }

.Marvin-1 { /* 1 */ }
.Marvin-2 { /* 2 */ }
.Marvin-3 { /* 3 */ }

.Marvin-1R { /* 1R */ }
.Marvin-2R { /* 2R */ }
.Marvin-3R { /* 3R */ }
.Marvin-4R { /* 4R */ }`
				}
			]}
		/>
	</div>
</Slide>
