<script>
	import About from '../components/About.svelte';
	import Footer from '../components/Footer.svelte';
	import Header from '../components/Header.svelte';
	import Product from '../components/Product.svelte';
	import Ready from '../components/Ready.svelte';
	import RisetInovasi from '../components/RisetInovasi.svelte';

  let PUBLIC_BASE_URL = "https://run-capital-landingpage.vercel.app"
</script>

<main>
	<Header />
	<About />
	<Product />
	<RisetInovasi />
	<Ready />
	<Footer />
</main>

<svelte:head>
	<title>Run Capital | Landing Page</title>
	<meta name="twitter:card" content="summary_large_image" />
	<meta property="twitter:domain" content={PUBLIC_BASE_URL} />
	<meta property="twitter:url" content={PUBLIC_BASE_URL} />
	<meta name="twitter:title" content="Run Capital" />
	<meta
		name="twitter:description"
		content="Raih Kebebasan Finansial Dengan Langkah Yang Tepat"
	/>
	<meta name="twitter:image" content="{PUBLIC_BASE_URL}/bg-social.jpg" />
	<meta property="og:title" content="Run Capital" />
	<meta property="og:type" content="website" />
	<meta property="og:url" content={PUBLIC_BASE_URL} />
	<meta property="og:image:url" content="{PUBLIC_BASE_URL}/bg-social.jpg" />
	<meta
		property="og:description"
		content="Raih Kebebasan Finansial Dengan Langkah Yang Tepat"
	/>
</svelte:head>

<style lang="postcss">
	:global(html) {
		background-color: theme(colors.gray.100);
	}
</style>
