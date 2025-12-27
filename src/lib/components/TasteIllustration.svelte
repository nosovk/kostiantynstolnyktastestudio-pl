<script lang="ts">
	import herbs from '$lib/assets/herbs-and-spices.svg';

	// Simple floating animation using CSS
</script>

<div class="illustration-container">
	<img src={herbs} alt="" class="herbs-bg" />
	<svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg" class="floating-svg">
		<defs>
			<linearGradient id="taste-gradient" x1="0%" y1="0%" x2="100%" y2="100%">
				<stop offset="0%" style="stop-color:#FF9A9E;stop-opacity:1" />
				<stop offset="100%" style="stop-color:#FECFEF;stop-opacity:1" />
			</linearGradient>
		</defs>
		<path
			fill="url(#taste-gradient)"
			d="M45.7,-76.3C58.9,-69.3,69.1,-55.6,76.5,-41.2C83.9,-26.8,88.5,-11.7,85.8,2.1C83.1,15.9,73.1,28.4,63.1,39.6C53.1,50.8,43.1,60.7,31.4,66.9C19.7,73.1,6.3,75.6,-6.6,74.5C-19.5,73.4,-31.9,68.7,-43.3,61.1C-54.7,53.5,-65.1,43,-72.4,30.3C-79.7,17.6,-83.9,2.7,-81.2,-11.1C-78.5,-24.9,-68.9,-37.6,-57.2,-47.5C-45.5,-57.4,-31.7,-64.5,-17.8,-67.2C-3.9,-69.9,10.1,-68.2,23.3,-66.5"
			transform="translate(100 100)"
		/>
		<!-- Some bubbles/particles -->
		<circle cx="150" cy="50" r="5" fill="#FF9A9E" class="bubble b1" />
		<circle cx="50" cy="150" r="8" fill="#FECFEF" class="bubble b2" />
		<circle cx="40" cy="60" r="4" fill="#FF9A9E" class="bubble b3" />
	</svg>
</div>

<style>
	.illustration-container {
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		position: relative;
	}

	.herbs-bg {
		position: absolute;
		width: 160%;
		max-width: 600px;
		opacity: 0.1;
		z-index: 0;
		animation: rotate-slow 120s linear infinite;
		pointer-events: none;
	}

	.floating-svg {
		z-index: 1;
		width: 300px;
		height: 300px;
		animation: float 6s ease-in-out infinite;
	}

	.bubble {
		opacity: 0.6;
	}
	.b1 {
		animation: float-bubble 4s ease-in-out infinite;
	}
	.b2 {
		animation: float-bubble 5s ease-in-out infinite reverse;
	}
	.b3 {
		animation: float-bubble 3s ease-in-out infinite 1s;
	}

	@keyframes float {
		0% {
			transform: translateY(0px);
		}
		50% {
			transform: translateY(-20px);
		}
		100% {
			transform: translateY(0px);
		}
	}

	@keyframes float-bubble {
		0% {
			transform: translateY(0px);
		}
		50% {
			transform: translateY(-10px);
		}
		100% {
			transform: translateY(0px);
		}
	}

	@keyframes rotate-slow {
		from {
			transform: rotate(0deg);
		}
		to {
			transform: rotate(360deg);
		}
	}
</style>
