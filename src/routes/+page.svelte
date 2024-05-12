<script>
	import About from '../components/About.svelte';
	import Footer from '../components/Footer.svelte';
	import Header from '../components/Header.svelte';
	import Product from '../components/Product.svelte';
	import Ready from '../components/Ready.svelte';
	import RisetInovasi from '../components/RisetInovasi.svelte';
</script>

<main>
	<Header />
	<About />
	<Product />
	<RisetInovasi />
	<Ready />
	<Footer />
</main>

<head>
  <title>Run Capital | Landing Page</title>
</head>

<style lang="postcss">
	:global(html) {
		background-color: theme(colors.gray.100);
	}
</style>
