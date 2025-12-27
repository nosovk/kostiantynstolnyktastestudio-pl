<script lang="ts">
	import { paint } from './gradient';
	import herbs from '$lib/assets/herbs-and-spices.svg';

	let canvas: HTMLCanvasElement;

	$effect(() => {
		const context = canvas.getContext('2d');
		if (!context) return;

		let frame = requestAnimationFrame(function loop(t) {
			frame = requestAnimationFrame(loop);
			paint(context, t);
		});

		return () => {
			cancelAnimationFrame(frame);
		};
	});
</script>

<div class="illustration-container">
	<canvas bind:this={canvas} width={32} height={32} style:--mask-image="url({herbs})"></canvas>
</div>

<style>
	.illustration-container {
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		min-width: 500px;
	}

	canvas {
		width: 100%;
		max-width: 400px;
		aspect-ratio: 1;

		mask-image: var(--mask-image);
		mask-position: center;
		mask-repeat: no-repeat;
		mask-size: contain;
		-webkit-mask-image: var(--mask-image);
		-webkit-mask-position: center;
		-webkit-mask-repeat: no-repeat;
		-webkit-mask-size: contain;

		/* Optional: makes the low-res canvas look pixelated instead of blurry */
		image-rendering: pixelated;
	}
</style>
