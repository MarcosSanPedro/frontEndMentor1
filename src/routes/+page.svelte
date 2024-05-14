<script lang="ts">
	import DropDown from '../lib/dropDown.svelte';
	import heroMobile from '../lib/images/image-hero-mobile.png';
	import Brands from '$lib/brands.svelte';
	import heroDesktop from '$lib/images/image-hero-desktop.png';

	const lines = ['Work', ' ', ' Remote', ' ', 'Work'];
</script>

<DropDown />

<img class="md:hidden mt-3" src={heroMobile} alt="Hero Images" />
<div class=" md:hidden flex flex-col items-center gap-3 p-3">
	<h2 class="text-5xl font-bold whitespace-nowrap">Make remote work</h2>
	<p class=" text-xl px-3 text-center text-gray-600">
		Get your team in sync, no matter your location. Streamline processes, create team rituals, and
		watch productivity soar
	</p>
	<button class="py-4 px-7 text-xl my-4 text-white bg-black rounded-2xl">Learn More</button>
	<Brands />
</div>

<div class=" hidden md:flex lg:px-20 xl:gap-52 items-center justify-center">
	<div class=" flex flex-col gap-5 xl:gap-10 p-3 Lg:w-4/5">
		<h1 class="text-7xl xl:text-8xl font-bold">
			Make
			<br /> <span class=" whitespace-nowrap">remote work</span>
		</h1>
		<p class=" text-2xl px-3 text-gray-600">
			Get your team in sync, no matter your location. Streamline processes, create team rituals, and
			watch productivity soar
		</p>
		<button class="py-4 px-7 text-xl w-40 m-auto my-4 text-white bg-black rounded-2xl"
			>Learn More</button
		>
		<Brands />
	</div>
	<img class=" w-[300px] xl:w-[460px] mr-10 xlmr-20" src={heroDesktop} alt="hero" />
</div>
