<script>
	export let title = 'star';
	export let filled = false;
	export let starId;
</script>
<style>
	.star {
		margin-right: 4px;
	}
	.starPath {
		fill: none;
		stroke: #abce0f;
		stroke-width: 3;
	}
	.filled {
		fill: rgb(242, 110, 209);
	}
</style>

<svg xmlns="http://www.w3.org/2000/svg" width="32" height="31" viewBox="0 0 51 48" class="star" on:mouseover on:mouseleave on:click data-starid={starId} let:class>
	<title>{title}</title>
	<path class:filled  data-starid={starId} class="starPath" d="m25,1 6,17h18l-14,11 5,17-15-10-15,10 5-17-14-11h18z" />
</svg>