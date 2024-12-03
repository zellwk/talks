<script lang="ts">
	import { Code, Slide, Transition } from '@animotion/core'

	let items = $state([1, 2, 3])
</script>

<Slide class="Slide">
	<h1 class="title">Responsive Typography</h1>
</Slide>

<Slide class="Slide">
	<Transition>
		<div class="Horizontal items-center gap-16">
			{#each items as item, i (item)}
				<h2
					class="BigText text-cPink-500 text-center"
					class:text-cPink-500={item === 1}
					class:text-cYellow-500={item === 2}
					class:text-cTurquoise-500={item === 3}
				>
					{#if item === 1}Fluid Type{/if}
					{#if item === 2}VS{/if}
					{#if item === 3}Responsive Type{/if}
				</h2>
			{/each}
		</div>
	</Transition>
</Slide>

<Slide class="Slide">
	<div class="Vertical">
		<h2 class="text-cPink-500">Fluid Typography</h2>
		<div>
			<Code
				lang="scss"
				codes={[
					`:root {
  --step--2: clamp(0.7813rem, 0.7747rem + 0.0326vw, 0.8rem);
  --step--1: clamp(0.9375rem, 0.9158rem + 0.1087vw, 1rem);
  --step-0: clamp(1.125rem, 1.0815rem + 0.2174vw, 1.25rem);
  --step-1: clamp(1.35rem, 1.2761rem + 0.3696vw, 1.5625rem);
  --step-2: clamp(1.62rem, 1.5041rem + 0.5793vw, 1.9531rem);
  --step-3: clamp(1.944rem, 1.771rem + 0.8651vw, 2.4414rem);
  --step-4: clamp(2.3328rem, 2.0827rem + 1.2504vw, 3.0518rem);
  --step-5: clamp(2.7994rem, 2.4462rem + 1.7658vw, 3.8147rem);
}`,
					`:root {
  @include utopia.generateTypeScale((
    "minWidth": 320,
    "maxWidth": 1240,
    "minFontSize": 18,
    "maxFontSize": 20,
    "minTypeScale": 1.2,
    "maxTypeScale": 1.25,
    "positiveSteps": 5,
    "negativeSteps": 2,
    "prefix": "step-",
    "relativeTo": "viewport-width"
  ));
}`
				]}
			/>
		</div>
	</div>
</Slide>

<Slide class="Slide">
	<div class="Vertical gap-6">
		<h2 class="text-cTurquoise-500">Responsive Typography</h2>
		<div>
			<Code
				lang="scss"
				codes={[
					`h1 {
  font-size: 3rem; 
  @media (width >= 800px) {
    font-size: 4rem;
  }
}`,
					`h1 {
  font-size: 3rem; 
  @media (width >= 800px) {
    font-size: 4rem;
  }
}

h2 {
  font-size: /* ... */; 
  @media (width >= 800px) {
    font-size: /* ... */ 
  }
}`,
					`h1 {
  font-size: 3rem; 
  @media (width >= 800px) {
    font-size: 4rem;
  }
}

h2 {
  font-size: /* ... */; 
  @media (width >= 800px) {
    font-size: /* ... */ 
  }
}

h3 {
  font-size: /* ... */; 
  @media (width >= 800px) {
    font-size: /* ... */ 
  }
}`
				]}
			/>
		</div>
	</div>
</Slide>

<Slide class="Slide">
	<h1 class="title !text-main">(╯°□°）╯︵ ┻━┻</h1>
</Slide>

<Slide class="Slide">
	<h1 class="title">Why Responsive Typography?</h1>
</Slide>

<Slide class="Slide">
	<img class="h-[500px] w-[900px]" src="/images/type-triangle.png" />
</Slide>
