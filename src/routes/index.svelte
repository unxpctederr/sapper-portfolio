
<script>
	import FeaturedGallery from "../components/FeaturedGallery.svelte";
	import Hero from "../components/Hero.svelte"
</script>

<svelte:head>
	<title>Matthew Hilton</title>
</svelte:head>

<style>
	h3 {
		background-color: #1b2225;
		color: white;
		margin: 0;
	}

	#more {
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	#more > div {
		background-color: #1b2225;
		display: flex;
		align-items: center;
		justify-content: flex-end;
		border-radius: 8px;
		padding: 20px;
		margin-top: 50px;
	}
</style>

<Hero />

<FeaturedGallery />

<a href="/work#other" id="more">
	<div>
		<h3> View More Projects </h3>
	</div>
</a>

