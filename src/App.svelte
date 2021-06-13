<script lang="ts">
	import Tailwindcss from './Tailwindcss.svelte';
	import Header from './components/Headers/Header.svelte';
	import Slider from './components/Slider/Slider.svelte';
	import Main from './components/Contents/Main.svelte';
	import Footer from './components/Footer/Footer.svelte';
</script>
<style>
	main { 
		font-family: "Gmarket Sans"
	}
</style>
<Tailwindcss />
<main class="w-full">
	<Header />
	<Slider />
	<Main />
	<Footer />
</main>