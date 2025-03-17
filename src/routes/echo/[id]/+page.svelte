<script lang="ts">
	import { onMount } from "svelte";
	import WaveSurfer from "wavesurfer.js";

	let container: HTMLElement;
	let wavesurfer;

	onMount(() => {
		const computedStyle = getComputedStyle(document.documentElement);
		const primaryHSL = computedStyle.getPropertyValue("--primary").trim();
		const secondaryHSL = computedStyle.getPropertyValue("--secondary").trim();

		wavesurfer = WaveSurfer.create({
			container,
			progressColor: `hsl(${primaryHSL})`,

			waveColor: `hsl(${secondaryHSL})`,
			barGap: 2,
			barWidth: 4,
			url: "/test.mp3",
		});
	});
</script>

<Card class="">
	<div bind:this={container}></div>
</Card>
