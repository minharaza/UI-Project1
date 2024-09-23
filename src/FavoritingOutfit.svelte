<script>
	import { fade } from 'svelte/transition';
	let Favorited = true;
</script>

<label>
	<input type="checkbox" bind:checked={Favorited} />
	Would you like to favorite this outfit?
</label>

{#if Favorited}
	<p transition:fade>Fades in and out</p>
{/if}
