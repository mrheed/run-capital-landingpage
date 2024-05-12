<script>
	let activeIndex = 0;
	let daftarInfo = [
		{
			title: 'Kinerja Investasi yang Unggul',
			content: `Run Capital memiliki catatan kinerja investasi yang kuat dan konsisten. Kami telah sukses menghasilkan investasi yang menguntungkan bagi para investor kami dalam berbagai kondisi pasar. Dengan fokus pada risiko yang terukur dan strategi investasi yang cermat, kami berkomitmen untuk memberikan hasil yang memuaskan bagi para pelanggan kami.`
		},
		{
			title: 'Transparency and Security',
			content: `
					Kami memprioritaskan transparansi dan keamanan dalam semua aspek layanan kami. Mulai dari
					proses investasi hingga pelaporan hasil, kami memberikan informasi yang jelas dan mudah
					dipahami oleh para investor. Selain itu, kami menerapkan langkah-langkah keamanan yang
					ketat untuk melindungi data dan aset keuangan pelanggan kami, sehingga Anda dapat
					berinvestasi dengan percaya diri.
      `
		},
		{
			title: 'Pendekatan Berbasis Teknologi',
			content: `Run Capital menggunakan teknologi mutakhir dalam pengelolaan investasi. Dengan pendekatan berbasis data dan analisis yang canggih, kami dapat mengidentifikasi peluang investasi yang menjanjikan dan mengoptimalkan portofolio secara efisien. Ini memastikan bahwa investasi Anda dikelola dengan cara yang paling efektif dan dapat menghasilkan hasil yang optimal dalam jangka panjang.`
		}
	];

	// @ts-ignore
	const onClickWhy = (index) => {
		return () => {
			if (activeIndex == index) {
				activeIndex = -1;
			} else {
				activeIndex = index;
			}
		};
	};

	// @ts-ignore
	$: {
		console.log(activeIndex);
	}
</script>

<div class="side-wrapper relative bg-navy">
	<div class="move-up bg-gray-200 py-24 px-16 flex">
		<div class="left flex flex-col gap-8 w-6/12">
			<h1 class="text-4xl font-bold px-12">Mengapa Berinvestasi di Run Capital?</h1>
			<div class="flex flex-col gap-6">
				{#each daftarInfo as item, index}
					{#if activeIndex != index}
						<!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
						<!-- svelte-ignore a11y-click-events-have-key-events -->
						<h2
							class="text-3xl font-medium cursor-pointer hover:text-sky-800 px-12"
							on:click={onClickWhy(index)}
						>
							{item.title}
						</h2>
					{:else}
						<div class="border-s-4 border-sky-600 px-12">
							<!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
							<!-- svelte-ignore a11y-click-events-have-key-events -->
							<h2
								class="text-3xl mb-2 text-sky-600 font-medium cursor-pointer hover:text-sky-800"
								on:click={onClickWhy(index)}
							>
								{item.title}
							</h2>
							<p class="text-lg text-gray-600 mb-4 leading-8">{item.content}</p>
							<a href="#" class="text-lg font-medium text-sky-600">Learn more</a>
						</div>
					{/if}
				{/each}
			</div>
		</div>
		<div class="right flex justify-center items-center">
			<img src="ball.png" width="80%" alt="Ball" />
		</div>
	</div>

	<div class="mt-20 px-16 move-up">
		<h3 class="text-white text-xl">Tentang Run Capital</h3>
		<div class="flex gap-32 mt-12">
			<img src="logo-only-white.png" width="200px" alt="Logo Only" />
			<p class="flex-1 text-gray-300 font-light text-xl">
				Platform investasi online dengan fitur-fitur yang mudah digunakan, beragam produk investasi,
				edukasi keuangan, dan smart contract. Dengan adanya fitur tersebut pengguna dapat menikmati
				keuntungan berupa kemudahan, keamanan, peningkatan pemahaman, dan transparansi.
			</p>
      <div class="flex-1 flex flex-col gap-8 justify-between">
			<p class="text-gray-300 font-light text-xl">
				Hal ini memberikan manfaat bagi pengguna untuk memulai investasi dengan mudah, mengembangkan
				portofolio dengan aman, serta merasakan pengurangan risiko dan peningkatan kepercayaan.
			</p>
      <a href="#" class="text-sky-600 hover:text-sky-800 font-medium text-xl">Learn more</a>
      </div>
		</div>
	</div>
</div>

<style>
	.move-up {
		transform: translateY(-8em);
	}
</style>
