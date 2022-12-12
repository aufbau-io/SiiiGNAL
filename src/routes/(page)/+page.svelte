<script>
	import { onMount } from 'svelte';
	let Geometry;

	onMount(async () => {
		const module = await import('$lib/components/geometry/geometry.svelte');
		Geometry = module.default;
	});
</script>

<main>
	<svelte:component this={Geometry} />
	<!-- <div class="sidebar">
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
	</div> -->
</main>

<style>
	main {
		position: relative;
		height: 100vh;
		overflow: hidden;
		display: flex;
	}

	.sidebar {
		position: absolute;
		top: 0;
		left: 0;
		display: flex;
		flex-flow: column nowrap;
		border-right: solid 1px var(--white-50);
		color: var(--black);

		padding: 20px;
	}

	.geometry {
		width: calc(100vw / 4 * 3);
	}
</style>
