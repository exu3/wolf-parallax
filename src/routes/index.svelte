<script>
	const layers = [0, 1, 2, 3, 4, 5];

	let y;
	let w;
</script>

<svelte:window bind:scrollY={y} bind:innerWidth={w} />

<div class="parallax-container" style="margin-top: -20px">
	{#each [0, 1, 2, 3, 4, 5] as layer}
		<img
			style="transform: translate(0,{(-y * layer) / (layers.length - 1)}px)"
			src="/layers/{layer}.png"
			alt="NeoHacks wolf parallax {layer}"
		/>
	{/each}
</div>

<div class="copy">
	<div class="foreground" style="top: {w * 0.6566 - 40}px">
		<h1>eebydeeby</h1>
		<p>awljlaskjd flaskdfjl wef awefjlkalskdfj</p>
	</div>
</div>

<style>
	.parallax-container {
		position: fixed;
		width: 100%;
		height: 100%;
		left: 50%;
		transform: translate(-50%, 0);
	}

	.parallax-container img {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		will-change: transform;
	}

	.parallax-container img:last-child::after {
		content: '';
		position: absolute;
		width: 100%;
		height: 100%;
		background: rgb(11, 10, 29);
	}

	.copy {
		position: relative;
		width: 100%;
		height: 100vh;
		text-align: center;
		box-sizing: border-box;
	}

	.foreground {
		position: absolute;
		left: 0;
		width: 100%;
		height: 100%;
		background-color: rgb(11, 10, 29);
		color: white;
		padding: 3rem 0.5rem 1rem 0.5rem;
	}
	:global(body) {
		margin: 0;
		padding: 0;
		background: linear-gradient(#1a1b67, #3b51a8);
	}
</style>
