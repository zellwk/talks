<script lang="ts">
	import { Action, Slide, Transition } from '@animotion/core'
	import { all, tween } from '@animotion/motion'

	let t1 = tween({ top: '-8rem', left: '-8rem', rotate: '-15deg', duration: 100 })
	let t2 = tween({ top: '-8rem', right: '-8rem', rotate: '15deg', duration: 100 })
	let t3 = tween({ bottom: '-8rem', left: '-8rem', rotate: '15deg', duration: 100 })
	let t4 = tween({ bottom: '-8rem', right: '-8rem', rotate: '-15deg', duration: 100 })
</script>

<!-- 
<Slide class="Slide">
	<div class="Stack">
		<div
			class="Tool Pos-topleft Marvin-2 text-cLightBlue-500 relative"
			style:top={t1.top}
			style:left={t1.left}
			style:transform={`rotateZ(${t1.rotate})`}
		>
			Tailwind
		</div>
		<div
			class="Tool Pos-topright Marvin-2 relative text-[hotpink]"
			style:top={t2.top}
			style:right={t2.right}
			style:transform={`rotateZ(${t2.rotate})`}
		>
			CSS
		</div>
		<div
			class="Tool Pos-bottomleft Marvin-2 relative text-[#dd3a0a]"
			style:bottom={t3.bottom}
			style:left={t3.left}
			style:transform={`rotateZ(${t3.rotate})`}
		>
			PostCSS
		</div>
		<div
			class="Tool Pos-bottomright Marvin-2 relative text-[#cf649a]"
			style:bottom={t4.bottom}
			style:right={t4.right}
			style:transform={`rotateZ(${t4.rotate})`}
		>
			Sass
		</div>
		<h1 class="Pos-center HeroHeading text-center">Tools</h1>
	</div>
</Slide> -->

<!-- <Slide class="Slide">
	<img alt="" src="/images/carpenter.png" />
</Slide> -->

<Slide class="Slide">
	<div class="Stack">
		<div
			class="Tool Pos-topleft Marvin-2 text-cLightBlue-500 relative"
			style:top={t1.top}
			style:left={t1.left}
			style:transform={`rotateZ(${t1.rotate})`}
		>
			Tailwind
		</div>
		<div
			class="Tool Pos-topright Marvin-2 relative text-[hotpink]"
			style:top={t2.top}
			style:right={t2.right}
			style:transform={`rotateZ(${t2.rotate})`}
		>
			CSS
		</div>
		<div
			class="Tool Pos-bottomleft Marvin-2 relative text-[#dd3a0a]"
			style:bottom={t3.bottom}
			style:left={t3.left}
			style:transform={`rotateZ(${t3.rotate})`}
		>
			PostCSS
		</div>
		<div
			class="Tool Pos-bottomright Marvin-2 relative text-[#cf649a]"
			style:bottom={t4.bottom}
			style:right={t4.right}
			style:transform={`rotateZ(${t4.rotate})`}
		>
			Sass
		</div>
		<h1 class="Pos-center HeroHeading text-center">Tools</h1>
	</div>

	<Action
		do={async () => {
			await all(
				t1.to({ top: '-4rem', left: '0', rotate: '0deg' }),
				t2.to({ top: '-4rem', right: '0', rotate: '0deg' }),
				t3.to({ bottom: '-4rem', left: '0', rotate: '0deg' }),
				t4.to({ bottom: '-4rem', right: '0', rotate: '0deg' })
			)
		}}
	/>

	<style>
		.Tool {
			transition: ease-out 0.3s;
			transition-property: top, bottom, left, right, transform;
		}
	</style>
</Slide>

<!-- Animation to break apart -->
<Slide class="Slide">
	<Transition><h1 class="text-cPink-500"><span>NOT</span></h1></Transition>
	<h1><span>Best</span></h1>
	<h1><span>Practices</span></h1>
</Slide>
