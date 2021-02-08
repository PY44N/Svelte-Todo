<script>
	import { each } from "svelte/internal";
	import Item from "./Item.svelte";
	import NavBar from "./NavBar.svelte";

	let todos = [];

	let text = "";

	function add() {
		todos = [...todos, text];
		text = "";
	}
</script>

<svelte:head>
	<link href="https://www.astrocore.net/style.css" rel="stylesheet" type="text/css" />
</svelte:head>

<NavBar />
<center>
	<input bind:value={text} placeholder="Todo" />
	<button on:click={add}>Add</button>

	{#each todos as todo}
		<Item text={todo} />
	{/each}
</center>
