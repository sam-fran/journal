<script>
	import "./layout.css";
	import icon from "$lib/assets/icon.svg";

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={icon} />
	<title>My Journal</title>
</svelte:head>

<div class="w-full min-h-screen dark:bg-blue-950 dark:text-amber-50">
	<nav class="flex w-full items-center justify-between px-8 py-7">
		<a href="/" class="flex items-center">
			<img src={icon} alt="Logo" class="h-16 w-auto m-auto mr-5" />
			<h2 class="text-3xl">My Journal</h2>
		</a>
		<div
			class="flex items-center space-x-4 text-gray-800 dark:text-amber-100 font-semibold"
		>
			<a
				href="/"
				class=" px-4 py-2 rounded hover:bg-gray-100 dark:hover:bg-blue-600 text-lg"
				>Home</a
			>
			<a
				href="/new"
				class="px-4 py-2 rounded hover:bg-gray-100 dark:hover:bg-blue-600 text-lg"
				>New Entry</a
			>
		</div>
	</nav>
	<hr class="border-none bg-linear-to-r from-cyan-500 to-purple-500 h-5" />
	<main class="p-10">
		{@render children()}
	</main>
	<footer class="text-center">© Sammy Pallas 2026</footer>
	<br />
	<hr class="border-none bg-linear-to-r from-green-500 to-cyan-500 h-5" />
</div>
