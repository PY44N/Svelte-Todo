<script>
	export let text;
	let done = false;
	let visible = true;
</script>

<style>
	.completed {
		text-decoration: line-through;
		color: rgb(1, 209, 1);
	}

	.notcompleted {
		color: white;
	}
</style>

{#if visible}
	<div class="TodoDiv">
		<h4 class={done ? "completed" : "notcompleted"}>{text}</h4>
		<button on:click={() => done = !done}>{done ? "✔️" : "❌"}</button>
		<button	button on:click={() => visible = false}>🗑️</button>
	</div>
{/if}
