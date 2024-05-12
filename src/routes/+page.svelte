<script>
	import About from '../components/About.svelte';
	import Header from '../components/Header.svelte';
	import Product from '../components/Product.svelte';
	import RisetInovasi from '../components/RisetInovasi.svelte';
</script>

<main>
	<Header />
	<About />
  <Product />
  <RisetInovasi />
</main>

<style lang="postcss">
	:global(html) {
		background-color: theme(colors.gray.100);
	}
</style>
