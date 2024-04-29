<script lang="ts">
import DropDown from "../lib/dropDown.svelte"
	import heroMobile from '../lib/images/image-hero-mobile.png'
	import toggleMenu from '$lib/dropDown.svelte'
</script>

<DropDown/>
<img src={heroMobile} alt="">


<div class=" {toggleMenu ? 'bg-black opacity-50' : 'bg-white'} flex flex-col items-center p-3">
<h2 class="text-5xl">Make remote work</h2>
<p>Get your team in sync, no matter your location. Streamline processes, create team rituals, and watch productivity soar</p>
<button class="p-6 text-white bg-black rounded-2xl">Learn More</button>
</div>

