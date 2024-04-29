<script lang="ts">
	import Flechita from '$lib/images/icon-arrow-up.svelte';
	import Logo from '$lib/images/logo.svelte';
	import CloseMenu from '$lib/images/icon-menu.svelte';
	import Menu from '$lib/images/icon-close-menu.svelte';
	import TodoList from '$lib/images/icon-todo.svelte';
	import Reminders from '$lib/images/icon-reminders.svelte';
	import IconPlanning from './images/icon-planning.svelte';
	import IconCalendar from './images/icon-calendar.svelte';

	let toggleFirst = $state(false);
	let toggleSecond = $state(false);
	let { toggleMenu = false } = $props();

	function toggleFirstMenu() {
		toggleFirst = !toggleFirst;
	}
	function toggleSecondMenu() {
		toggleSecond = !toggleSecond;
	}

	function toggleSidedMenu() {
		toggleMenu = !toggleMenu;
	}
</script>

<div class="sticky top-0 bg-white text-xl">
	<nav class="hidden md:flex justify-between py-3 px-8">
		<div class="flex md:gap-5 lg:gap-20 w-1/2 items-center">
			<span> <Logo /></span>
			<div>
				<button onclick={toggleFirstMenu} class="whitespace-nowrap"
					>Features<span>
						<Flechita />
					</span></button
				>
				{#if toggleFirst}
					<div class=" absolute text-base bg-white rou    nded-lg mt-3 p-5 shadow-lg shadow-gray-500">
						<ul class="flex flex-col gap-2">
							<li class=" flex items-center gap-2">
								<TodoList />
								Todo List
							</li>
							<li class=" flex items-center gap-2">
								<IconCalendar />
								History
							</li>
							<li class=" flex items-center gap-2">
								<Reminders />
								Reminders
							</li>
							<li class=" flex items-center gap-2">
								<IconPlanning />
								Planning
							</li>
						</ul>
					</div>
				{/if}
			</div>
			<div>
				<button class="whitespace-nowrap" onclick={toggleSecondMenu}
					>Company<span>
						<Flechita />
					</span></button
				>
				{#if toggleSecond}
					<div class="absolute text-base bg-white rounded-lg mt-3 p-5 shadow-lg shadow-gray-500">
						<ul class="flex flex-col gap-2">
							<li class=" flex items-center gap-2">History</li>
							<li>Our Team</li>
							<li>Blog</li>
						</ul>
					</div>
				{/if}
			</div>
			<button>Careers </button>
			<button>About </button>
		</div>
		<div class=" flex gap-5">
			<button>Login</button>
			<button class="border-black rounded-lg border p-2">Register</button>
		</div>
	</nav>
	<nav class=" relative bg-white md:hidden z-10 flex justify-between w-full items-center px-7 py-4">
		<div>
			<Logo />
		</div>
		<button onclick={toggleSidedMenu}>
			{#if toggleMenu}
				<Menu />
			{:else}
				<CloseMenu />
			{/if}
		</button>
	</nav>
	<button
		onclick={toggleSidedMenu}
		class="h-screen overflow-x-hidden w-full absolute top-0 left-0 bg-black/40 z-0 {toggleMenu
			? 'block translate-x-0'
			: 'hidden'} "
	></button>
	{#if toggleMenu}
		<div class="h-screen w-4/5 absolute right-0 z-10 bg-white pl-7 text-3xl flex flex-col gap-3">
			<h3 class=" font-bold">Features</h3>
			<ul class="flex flex-col gap-2 ml-9 text-2xl">
				<li class=" flex items-center gap-2">
					<TodoList />
					Todo List
				</li>
				<li class=" flex items-center gap-2">
					<IconCalendar />
					Calendar
				</li>
				<li class=" flex items-center gap-2">
					<Reminders />
					Reminders
				</li>
				<li class=" flex items-center gap-2">
					<IconPlanning />
					Planning
				</li>
			</ul>
			<h3 class=" font-bold mt-3">Company</h3>
			<ul class="flex flex-col gap-3 ml-9 text-2xl">
				<li class=" flex items-center gap-2">Calendar</li>
				<li>Our Team</li>
				<li>Blog</li>
			</ul>
			<span class=" font-bold">Careers</span>
			<span class=" font-bold">About us</span>

			<div class=" flex flex-col items-center gap-3 text-2xl mt-3">
				<button class="w-full">Login</button>
				<button class=" w-4/5 rounded-lg p-3 border border-black">Register</button>
			</div>
		</div>
	{/if}
</div>
