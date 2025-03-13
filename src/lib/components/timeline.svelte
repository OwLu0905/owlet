<script lang="ts">
	let { title = '123' } = $props();
</script>

{#snippet timelineBlock({ title }: { title: string })}
	<div
		class="relative mx-4 mb-1.5 mt-2.5 flex min-h-20 gap-2 border-l transition-all duration-150 ease-linear hover:border-l-2 hover:border-gray-300 hover:bg-gray-100"
	>
		<div class="absolute -left-3 h-6 w-6 rounded-full border-4 border-white bg-primary"></div>
		<div class="container">
			<div class="vertical-line"></div>
		</div>
		<div class="flex flex-col px-6">
			<h6 class="text-sm">{title}</h6>
			<p class="m-auto text-xs">Lorem ipsum dolor sit amet...</p>
		</div>
	</div>
{/snippet}

{@render timelineBlock({ title: title })}

<style>
	.container {
		height: 200px;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.vertical-line {
		width: 0; /* Start with width 0 */
		height: 0; /* Start with height 0 */
		background-color: black;
		position: absolute;
		bottom: 0;
		animation: grow-line 2s forwards;
	}

	@keyframes grow-line {
		0% {
			width: 0;
			height: 0;
		}
		100% {
			width: 4px;
			height: 200px; /* Grow to full height */
		}
	}
</style>
