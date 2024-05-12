<script>
	let sideMenu = ['Articles', 'Videos', 'White Papers'];
	let activeMenu = 0;

	let articlesData = [
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

	let videosData = [
		{
			title: 'Transformasi Industri Keuangan',
			tanggal: 'Jumat, Mar 21, 2024',
			img: 'videos/1.jpg'
		},
		{
			title: 'Meningkatkan Akses dan Kualitas Layanan ...',
			tanggal: 'Jumat, Mar 21, 2024',
			img: 'videos/2.jpg'
		},
		{
			title: 'Masa Depan Energi Terbarukan',
			tanggal: 'Jumat, Mar 21, 2024',
			img: 'videos/3.jpg'
		},
		{
			title: 'Kecerdasan Buatan dalam Keuangan',
			tanggal: 'Jumat, Mar 21, 2024',
			img: 'videos/4.jpg'
		},
		{
			title: 'Memahami Online Perilaku Investor',
			tanggal: 'Jumat, Mar 21, 2024',
			img: 'videos/5.jpg'
		},
		{
			title: 'Menggabungkan Teknologi dan Pertania...',
			tanggal: 'Jumat, Mar 21, 2024',
			img: 'videos/6.jpg'
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

<div class="bg-slate-100 relative">
  <img src="bg-video-section.png" class="absolute bottom-0" alt="bg video section">
	<div class="side-wrapper mx-16 py-24 grid grid-cols-5 gap-8">
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
				{#each articlesData as data}
					<div class="border border-gray-300 rounded-lg w-full">
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
			{:else if activeMenu == 1}
				{#each videosData as data}
					<div class="border border-gray-300 rounded-lg w-full video-card">
						<div class="img-wrapper relative" style="height: 220px;">
							<div
								class="absolute"
								style="z-index: 99; top: 50%; left: 50%; transform: translate(-50%, -50%)"
							>
								<img src="videos/play.png" alt="Play" />
							</div>
							<img
								src={data.img}
								alt={data.title}
								class="w-full h-full"
								style="object-fit: cover; object-position: center"
							/>
						</div>
						<div class="px-6 py-8 flex flex-col gap-2">
							<span class="font-light text-grey-600">{data.tanggal}</span>
							<a href="#" class="text-2xl font-bold text-sky-900 hover:text-sky-600">{data.title}</a
							>
						</div>
					</div>
				{/each}
			{:else if activeMenu == 2}
				{#each whitePapersData as data}
					<div class="border border-gray-300 rounded-lg w-full">
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

<style>
	.video-card .img-wrapper::after {
		content: '';
		width: 100%;
		height: 100%;
		top: 0;
		left: 0;
		background: #003852;
		position: absolute;
		opacity: 80%;
	}
</style>
