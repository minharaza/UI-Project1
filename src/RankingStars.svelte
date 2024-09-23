<!-- <script>
	import { fade, slide } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	import Star from './Star.svelte';
	
	// User rating states
	let rating = null;
	let hoverRating = null;
	
	// form interaction states
	let collectFeedback = false;
	let feedbackCompleted = false;
	
	// "$:" triggers when something in the line changes
	// When these variables reach true/false, they trigger these functions
	$: collectFeedback && addWatchListeners();
	$: !collectFeedback && feedbackFormClosed();
	
	function feedbackFormClosed() {
		feedbackCompleted = false;
		removeWatchListeners()
	}
	
	function addWatchListeners() {
		document.addEventListener('keydown', userDismissFeedback);
		document.addEventListener('click', userClickedOutsideOfFeedback);
	}
	function removeWatchListeners() {
		document.removeEventListener('keydown', userDismissFeedback);
		document.removeEventListener('click', userClickedOutsideOfFeedback);
	}
	function userClickedOutsideOfFeedback(event) {
		const container = document.getElementById('feedbackContiner');
		if (!container.contains(event.target)) {
			collectFeedback = false;
		}
	}
	function userDismissFeedback(event) {
			switch(event.key) {
				case 'Escape':
					collectFeedback = false;
					break;
				default:
					return;
			}
		}
	
	// using curried function to initialize hover with id
	const handleHover = (id) => () => {
		hoverRating = id;
	}
	const handleRate = (id) => (event) => {
		if (collectFeedback && 
				rating && 
				rating.toString() === event.srcElement.dataset.starid
		) {
			collectFeedback = false;
			return;
		}
		rating = id;
		collectFeedback = true;
	}
	
	let stars = [
		{ id: 1, title: 'One Star' },
		{ id: 2, title: 'Two Stars' },
		{ id: 3, title: 'Three Stars' },
		{ id: 4, title: 'Four Stars' },
		{ id: 5, title: 'Five Stars' },
	]

	function handleCollectFeedback(e) {
		const textarea = e.srcElement.querySelector('textarea');
		const value = textarea.value;
		
		// let them know we recieved it
		feedbackCompleted = true;
		
		// then reset view
		setTimeout(() => {
			collectFeedback = false;
			feedbackCompleted = false;
		}, 1250);
	}
	
	function handleLinkFeedback() {
		collectFeedback = true; 
	}
</script>
<style>
	.feedback {
		position: relative;
	}
	.starContainer {
		display: inline-block;
		transition: background .2s ease-out;
		border-radius: 8px;
		padding: 4px 6px 0;
	}
	.secondaryAction {
		margin: 8px;
		font-size: 12px;
		display: inline-block;
	}
	.feedbackContainerDisabled {
		pointer-events: none;
	}
	:global(button) {
		cursor: pointer;
	}
</style>

<div class="feedback"> 
	<span id="feedbackContiner" class="feedbackContainer" class:feedbackContainerDisabled={feedbackCompleted}>
		<span class="starContainer">
		{#each stars as star (star.id)}
			<Star 
					filled={hoverRating ? (hoverRating >= star.id) : (rating >= star.id)} 
					starId={star.id}
					on:mouseover={handleHover(star.id)} 
					on:mouseleave={() => hoverRating = null}
					on:click={handleRate(star.id)}
				/>
		{/each}
				</span>
				<br />
				<p class="secondaryAction">
					{#if rating !== null}
						Thank you for your feedback - <a href="#!" on:click={() => rating = null} on:click={(event) => window.confirim('Your feedback is very valuable. Are you sure you want to reset?') ? event.preventDefault() : null}>reset</a>
					{:else}
					<a href="#!" on:click={handleLinkFeedback}>Rate your outfit!</a>
					{/if}
			</p>
			<br />
		{#if collectFeedback} 
				<div class="collectFeedbackContainer" transition:fade>
					{#if feedbackCompleted} 
						<p>
							Thank you!
						</p>
					{/if}
				</div>
		{/if}
  </span>
</div> -->

<script>
	// This allows the parent component (e.g., App.svelte) to bind to the rating value
	export let value = 0; // Initial rating value (default: 0)
  
	// Function to set the rating when a user clicks on a star
	function setRating(newRating) {
	  value = newRating;
	}
  </script>
  
  <div class="stars-container">
	<!-- Iterate through 5 stars -->
	{#each Array(5) as _, index (index)}
	  <span 
		class="star" 
		on:click={() => setRating(index + 1)} 
		on:mouseover={() => hoverRating = index + 1}
		on:mouseleave={() => hoverRating = 0}
		>
		{#if value > index}
		  <!-- Filled star when the value is greater than the current index -->
		  ⭐
		{:else}
		  <!-- Empty star otherwise -->
		  ☆
		{/if}
	  </span>
	{/each}
  </div>
  
  <style>
	.stars-container {
	  display: inline-block;
	  cursor: pointer;
	}
  
	.star {
	  font-size: 2rem; /* Size of the stars */
	  color: #fe009d; /* Star color */
	  padding: 5px; /* Space between stars */
	  transition: transform 0.2s ease; /* Smooth transition effect when clicking or hovering */
	}
  
	.star:hover {
	  transform: scale(1.2); /* Slightly increase the size of the star when hovered */
	}
  </style>
  