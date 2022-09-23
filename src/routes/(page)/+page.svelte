<script>
	import { onMount } from 'svelte';
	let Geometry;

	onMount(async () => {
		const module = await import('$lib/components/geometry/geometry.svelte');
		Geometry = module.default;
	});
</script>

<main>
	<div class="sidebar">
		<h4>SiiiGNAL</h4>
		<h6>version: 0.0.1</h6>
		<h6>instructions</h6>
		<br />
		<h6>globe view [ <b>on</b> ]</h6>
		<h6>field view</h6>
		<br />
		<h6>rivers: [ <b>on</b> / off ]</h6>
		<h6>connections: [ <b>on</b> / off ]</h6>
		<br />
		<h6>START GAME</h6>
	</div>
	<svelte:component this={Geometry} />
</main>

<style>
	main {
		position: relative;
		height: 100vh;
		overflow: hidden;
		display: flex;
	}

	.sidebar {
		display: flex;
		flex-flow: column nowrap;
		width: calc(100vw / 4);
		border-right: solid 1px var(--white-50);

		padding: 20px;
	}

	.geometry {
		width: calc(100vw / 4 * 3);
	}
</style>
