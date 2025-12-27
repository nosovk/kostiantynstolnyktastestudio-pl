<script lang="ts">
	import { resolve } from '$app/paths';
	import { fade, fly } from 'svelte/transition';
	import TasteIllustration from '$lib/components/TasteIllustration.svelte';
</script>

<svelte:head>
	<title>Kostiantyn Stolnyk Taste Studio</title>
	<meta
		name="description"
		content="Kostiantyn Stolnyk Taste Studio - Producing different tastes for food."
	/>
</svelte:head>

<main>
	<section class="hero">
		<div class="content" in:fly={{ y: 50, duration: 1000, delay: 300 }}>
			<h1>Kostiantyn Stolnyk <br /><span class="highlight">Taste Studio</span></h1>
			<p class="tagline">We produce different tastes for food.</p>
			<a href="mailto:contact@kostiantynstolnyktastestudio.pl" class="cta-button">Contact Us</a>
		</div>

		<div class="visual" in:fade={{ duration: 1500 }}>
			<TasteIllustration />
		</div>
	</section>

	<footer class="legal-footer">
		<div class="container">
			<h2>Legal Information</h2>
			<div class="legal-grid">
				<div class="legal-item">
					<strong>Owner:</strong> Kostiantyn Stolnyk
				</div>
				<div class="legal-item">
					<strong>NIP:</strong> 7011289522
				</div>
				<div class="legal-item">
					<strong>Phone:</strong> <a href="tel:+48790346481">+48 790 346 481</a>
				</div>
				<div class="legal-item">
					<strong>Email:</strong>
					<a href="mailto:contact@kostiantynstolnyktastestudio.pl"
						>contact@kostiantynstolnyktastestudio.pl</a
					>
				</div>
				<div class="legal-item full-width">
					<strong>Delivery Address:</strong><br />
					Kostiantyn Stolnyk, woj. MAZOWIECKIE, pow. grodziski, gm. Milanówek, miejsc. Milanówek, ul.
					Warszawska, nr 1D, lok. 14, 05-822
				</div>
			</div>
			<div class="links">
				<a href={resolve('/privacy')}>Privacy Policy</a>
				<a href={resolve('/terms')}>Terms of Service</a>
			</div>
		</div>
	</footer>
</main>

<style>
	:global(body) {
		margin: 0;
		font-family: 'Inter', sans-serif;
		background-color: #fff9fc;
		color: #333;
	}

	main {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	.hero {
		flex: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 2rem;
		text-align: center;
	}

	@media (min-width: 768px) {
		.hero {
			flex-direction: row;
			text-align: left;
			justify-content: space-around;
			padding: 4rem;
		}
	}

	.content {
		max-width: 500px;
	}

	h1 {
		font-size: 2.5rem;
		line-height: 1.2;
		margin-bottom: 1rem;
		color: #2c3e50;
	}

	.highlight {
		color: #ff9a9e;
		background: -webkit-linear-gradient(#ff9a9e, #fecfef);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}

	.tagline {
		font-size: 1.2rem;
		color: #666;
		margin-bottom: 2rem;
	}

	.cta-button {
		display: inline-block;
		padding: 12px 24px;
		background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 100%);
		color: white;
		text-decoration: none;
		border-radius: 25px;
		font-weight: bold;
		transition:
			transform 0.2s,
			box-shadow 0.2s;
		box-shadow: 0 4px 15px rgba(255, 154, 158, 0.4);
	}

	.cta-button:hover {
		transform: translateY(-2px);
		box-shadow: 0 6px 20px rgba(255, 154, 158, 0.6);
	}

	.visual {
		margin-top: 2rem;
	}

	@media (min-width: 768px) {
		.visual {
			margin-top: 0;
			margin-left: 2rem;
		}
	}

	.legal-footer {
		background-color: #f8f9fa;
		padding: 3rem 1rem;
		border-top: 1px solid #eaeaea;
		font-size: 0.9rem;
	}

	.container {
		max-width: 900px;
		margin: 0 auto;
	}

	h2 {
		font-size: 1.2rem;
		margin-bottom: 1.5rem;
		color: #444;
		text-align: center;
	}

	.legal-grid {
		display: grid;
		grid-template-columns: 1fr;
		gap: 1rem;
		margin-bottom: 2rem;
	}

	@media (min-width: 600px) {
		.legal-grid {
			grid-template-columns: repeat(2, 1fr);
		}
	}

	.legal-item {
		background: white;
		padding: 1rem;
		border-radius: 8px;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.02);
		border: 1px solid #eee;
	}

	.full-width {
		grid-column: 1 / -1;
	}

	strong {
		color: #555;
		display: block;
		margin-bottom: 0.25rem;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.5px;
	}

	.legal-footer a {
		color: #ff9a9e;
		text-decoration: none;
	}

	.legal-footer a:hover {
		text-decoration: underline;
	}

	.links {
		text-align: center;
		margin-top: 2rem;
		display: flex;
		justify-content: center;
		gap: 1rem;
		color: #888;
	}

	.links a {
		color: #888;
	}
</style>
