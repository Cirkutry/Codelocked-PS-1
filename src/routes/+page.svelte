<script lang="ts">
	import Hero from "$lib/components/main/Hero.svelte";
	import Footer from "$lib/components/main/Footer.svelte";
    import NavBar from "$lib/components/main/NavBar.svelte";
	import HabitatStatus from "$lib/components/main/HabitatStatus.svelte";
    import CrewLog from "$lib/components/main/CrewLog.svelte";
    import Environment from "$lib/components/main/Environment.svelte";
    import Archive from "$lib/components/main/Archive.svelte";
</script>

<main>
		<NavBar />
		<Hero />
		<HabitatStatus />
		<CrewLog />
		<Environment />
		<Archive />
		<Footer />
</main>
