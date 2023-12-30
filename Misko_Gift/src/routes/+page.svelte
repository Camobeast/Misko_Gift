<script>
	import { fly } from "svelte/transition";
	let name = 'Miško';
	let showing = false;

	function handleClick() {
		showing = !showing;
	}
</script>

<h1 class="h1 text-fuchsia-700 py-5 text-center font-bold">Merry Christmas {name}!</h1>
<h2 class="h2 text-red-600 py-5 text-center underline underline-offset-4 font-semibold">Bellow you can find the picture of your present!</h2>

<div class="flex justify-center pt-20">
	<button on:click={handleClick} class="card p-4 w-96 h-auto flex flex-col items-center justify-center" id="present">
		{#if !showing}
			<h3 class="h3 text-red-500 py-5 text-center font-bold">Click to see your present!</h3>
		{:else}
			<img transition:fly={{ y: 800, duration: 1000 }} class="w-96" src="images/zidle.png" alt="Miskuv present - a chair">
		{/if}
	</button>
</div>

<div class="absolute bottom-0 m-auto flex justify-center">
	<h4 class="h5 text-red-500 py-5 text-center">Santa allows an exchange of this gift for a fidget toy with delivery around 14 days</h4>
</div>
