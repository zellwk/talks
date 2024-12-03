<script lang="ts">
	import { Slide, Transition } from '@animotion/core'
</script>

<Slide class="Slide">
	<table class="text-4xl">
		<thead>
			<tr>
				<th class="!p-12 !text-left">In CSS</th>
				<th class="!p-12 !text-left">In HTML</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td class="!p-12 !text-left">
					<Transition order={1}>Create components</Transition>
				</td>
				<td class="!p-12 !text-left">
					<Transition order={2}>Change values on the fly</Transition>
				</td>
			</tr>
			<tr>
				<td class="!p-12 !text-left">
					<Transition order={4}>Use <code>@apply</code></Transition>
				</td>
				<td class="!p-12 !text-left">
					<Transition order={3}>Use variants</Transition>
				</td>
			</tr>
		</tbody>
	</table>

	<Transition
		do={() => {
			width = '300px'
			cols = 1
		}}
	></Transition>
</Slide>
