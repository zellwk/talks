<script lang="ts">
	import { Action, Code, Slide } from '@animotion/core'

	let codeHTML: ReturnType<typeof Code>
	let codeCSS: ReturnType<typeof Code>
	let codeJS: ReturnType<typeof Code>
	let code2: ReturnType<typeof Code>
</script>

<Slide class="Slide">
	<h1 class="title">Responsive Type</h1>
</Slide>

<Slide class="Slide">
	<div class="Masonry [--cols:2]">
		<div>
			<Code bind:this={codeHTML} lang="html" code={`<h1> ... </h1>`} />
		</div>
		<div>
			<Code bind:this={codeJS} lang="js" code={``} />
		</div>
		<div>
			<Code
				bind:this={codeCSS}
				lang="css"
				code={`h1 {
  font-size: 3rem; 
  @media (width >= 800px) {
    font-size: 4rem;
  }
}`}
			/>
		</div>

		<Action
			do={async () => {
				await codeJS.update`export default {
  theme: {
    splendidResponsiveType: {
      // ...
    }
  }        
}`
				await codeJS.selectLines`3-5`
			}}
		/>

		<Action
			actions={[
				async () => {
					await codeJS.update`export default {
  theme: {
    splendidResponsiveType: {
      Marvin: {
        // ...
      }
    }
  }        
}`
					await codeJS.selectLines`4-6`
				},
				async () => {
					await codeJS.update`export default {
  theme: {
    splendidResponsiveType: {
      Marvin: {
        '1R': {
          // ...
        }
      }
    }
  }        
}`
					await codeJS.selectLines`5-7`
				},

				async () => {
					await codeJS.update`export default {
  theme: {
    splendidResponsiveType: {
      Marvin: {
        '1R': {
          base: '3rem',
        }
      }
    }
  }        
}`
					await codeJS.selectLines`6`
					await codeCSS.selectLines`1, 3-6`
				},

				async () => {
					await codeJS.update`export default {
  theme: {
    splendidResponsiveType: {
      Marvin: {
        '1R': {
          base: '3rem',
          bp8: '4rem',
        }
      }
    }
  }        
}`
					await codeJS.selectLines`7`
					await codeCSS.selectLines`1, 6`
				},

				async () => {
					await codeCSS.update`/* Output CSS */
.Marvin-1R {
  font-size: 3rem; 
  @media (width >= 800px) {
    font-size: 4rem;
  }
}`
					await codeCSS.selectLines`*`
				},

				async () => {
					await codeHTML.update`<h1 class="Marvin-1R"> ... </h1>`
					await codeHTML.selectToken`Marvin-1R`
				},

				async () => {
					await codeJS.update`export default {
  theme: {
    splendidResponsiveType: {
      Marvin: {
        '1R': {
          base: '3rem',
          bp8: '4rem',
          lg: '5rem',
        }
      }
    }
  }        
}`

					await codeCSS.update`/* Output CSS */
.Marvin-1R {
  font-size: 3rem; 
  @media (width >= 800px) {
    font-size: 4rem;
  }
	@media (width >= 1024px) {
		font-size: 5rem;
	}
}`
					await codeJS.selectLines`8`
					await codeCSS.selectLines`7-9`
				}
			]}
		/>
	</div>
</Slide>
