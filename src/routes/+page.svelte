<script>
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
	import gasm from '$lib/images/Gasm.gif';
	let show = false
	function showgif() {
		show = !show
	}
	//Clicking the button brings up a gif that plays on repeat
	// 
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<div class="grid place-items-center border-2 h-[900px] w-[600px] shadow-2xl rounded-xl bg-red-900">
	<h1 class= "grid place-items-center border-2 h-auto w-[450px] bg-green-600 rounded-xl opacity-80">My svelte page</h1>
	<button class="bg-blue-600 rounded-xl py-2 px-1 text-white hover:bg-blue-200 cursor-pointer" on:click = {showgif}>BUTTON</button>
	{#if show}
		<img transition:fade src={gasm} alt="" />
	{/if}
	<h2 class = "grid place-items-center border-2 bg-green-600 rounded-xl opacity-80">
		try editing <strong>src/routes/+page.svelte</strong>
	</h2>
		<div class = "grid place-items-center border-2 h-auto w-auto opacity-90 bg-purple-600 text-white rounded-xl">
		<Counter class = "text-white" />
		</div>
	</div>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
