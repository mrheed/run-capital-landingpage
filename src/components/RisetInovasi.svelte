<script>
	let sideMenu = ['Articles', 'Videos', 'White Papers'];
	let activeMenu = 0;

	let risetData = [
		{
			title: 'Bitcoin: Aset Bebas Risiko yang Unik?',
			img: 'riset/1.jpg'
		},
		{
			title: 'Teknologi Blockchain Membuka Investasi Bar...',
			img: 'riset/2.jpg'
		},
		{
			title: 'Sentimen Media Sosial Analisis untuk Olahraga...',
			img: 'riset/3.jpg'
		},
		{
			title: 'Memanfaatkan Data Besar Teknologi untuk Mening...',
			img: 'riset/4.jpg'
		},
		{
			title: 'Memahami Online Perilaku Investor',
			img: 'riset/5.jpg'
		},
		{
			title: 'Blockchain dan Masa Depan Investasi',
			img: 'riset/6.jpg'
		}
	];

	let whitePapersData = [
		{
			title: 'Revitalisasi Pariwisata Pasca-Pandemi',
			tanggal: 'Mar. 21, 2024',
			img: 'whitepapers/1.jpg'
		},
		{
			title: 'Mengungkap Potensi Pasar: Analisis Riset Ter...',
			tanggal: 'Mar. 21, 2024',
			img: 'whitepapers/1.jpg'
		},
		{
			title: 'Menavigasi Era Digital: Studi Kasus tentang P...',
			tanggal: 'Mar. 21, 2024',
			img: 'whitepapers/1.jpg'
		},
		{
			title: 'Mengoptimalkan Portofolio Investasi de...',
			tanggal: 'Mar. 21, 2024',
			img: 'whitepapers/1.jpg'
		},
		{
			title: 'Menggagas Solusi Keuangan Inklusif',
			tanggal: 'Mar. 21, 2024',
			img: 'whitepapers/1.jpg'
		},
		{
			title: 'Transformasi Industri Agrikultur: Pendekatan...',
			tanggal: 'Mar. 21, 2024',
			img: 'whitepapers/1.jpg'
		}
	];

	// @ts-ignore
	const onClickSideMenu = (index) => {
		return () => {
			activeMenu = index;
		};
	};

	// @ts-ignore
	$: activeMenu;
</script>

<div class="side-wrapper bg-gray-200">
	<div class="px-16 py-24 grid grid-cols-5 gap-8">
		<div></div>
		<div class="flex-1 col-span-4">
			<div class="flex flex-between">
				<h1 class="font-bold text-4xl text-sky-900">Riset Inovasi</h1>
			</div>
		</div>
		<ul class="font-bold text-lg text-sky-900">
			{#each sideMenu as menu, index}
				<!-- svelte-ignore a11y-click-events-have-key-events -->
				<!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
				<li
					class="my-4 hover:text-sky-600 {activeMenu == index ? 'text-sky-600' : ''} cursor-pointer"
					on:click={onClickSideMenu(index)}
				>
					{menu}
				</li>
			{/each}
		</ul>
		<div class="grid grid-cols-3 gap-8 col-span-4">
			{#if activeMenu == 0}
				{#each risetData as data}
					<div class="border border-gray-400 rounded-lg w-full">
						<div style="height: 220px;">
							<img
								src={data.img}
								alt={data.title}
								class="w-full h-full"
								style="object-fit: cover; object-position: center"
							/>
						</div>
						<div class="px-6 py-8 flex flex-col gap-2">
							<span class="font-light text-grey-600">Analyst Research</span>
							<a href="#" class="text-2xl font-bold text-sky-900 hover:text-sky-600">{data.title}</a
							>
						</div>
					</div>
				{/each}
			{:else if activeMenu == 2}
				{#each whitePapersData as data}
					<div class="border border-gray-400 rounded-lg w-full">
						<div style="height: 220px;">
							<img
								src={data.img}
								alt={data.title}
								class="w-full h-full"
								style="object-fit: cover; object-position: center"
							/>
						</div>
						<div class="px-6 py-8 flex flex-col gap-2">
							<span class="font-light text-grey-600">Diterbitkan : {data.tanggal}</span>
							<a href="#" class="text-2xl font-bold text-sky-900 hover:text-sky-600">{data.title}</a
							>
						</div>
					</div>
				{/each}
			{/if}
		</div>
	</div>
</div>
