<!-- <script>

	function handleClick() {
		alert('You are submitting!');
	}
</script>

<button class="submit-btn" on:click|once={handleClick}>Submit Entry</button>

<style>
	/* Styling for the submit button */
	.submit-btn {
		position: relative;
		top: -10px;
		background-color: #b7c537; /* Green background */
		color: white; /* White text */
		font-size: 18px; /* Font size */
		padding: 12px 24px; /* Padding */
		border: none; /* Remove default border */
		border-radius: 8px; /* Rounded corners */
		cursor: pointer; /* Pointer cursor on hover */
		box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1); /* Subtle shadow */
		transition: background-color 0.3s, transform 0.3s; /* Smooth transitions */
	}

	/* Hover effect */
	.submit-btn:hover {
		background-color: #a3e9f4; /* Darker green on hover */
		transform: translateY(-3px); /* Slight lift on hover */
	}

	/* Active (pressed) effect */
	.submit-btn:active {
		background-color: #163098; /* Even darker green */
		transform: translateY(0px); /* Return to original position */
	}

	/* Disabled state (optional) */
	.submit-btn:disabled {
		background-color: #cccccc; /* Gray background for disabled state */
		color: #666666; /* Gray text */
		cursor: not-allowed; /* No pointer cursor */
	}
</style>
 -->
 <script>
	import { createEventDispatcher } from 'svelte';
  
	// Create an event dispatcher to communicate with the parent component
	const dispatch = createEventDispatcher();
  
	// Function to handle the button click and emit a custom event
	function handleClick() {
	  dispatch('click'); // Dispatch a 'click' event to the parent
	}
  </script>
  
  <button class="submit-btn" on:click={handleClick}>
	Submit Entry
  </button>
  
  <style>
	.submit-btn {
	  background-color: #b7c537; /* Green background color */
	  color: white; /* White text */
	  font-size: 18px; /* Font size */
	  padding: 12px 24px; /* Padding around the button */
	  border: none; /* No border */
	  border-radius: 8px; /* Rounded corners */
	  cursor: pointer; /* Pointer cursor on hover */
	  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1); /* Subtle shadow */
	  transition: background-color 0.3s, transform 0.3s; /* Smooth transition for hover and click */
	}
  
	/* Hover effect */
	.submit-btn:hover {
	  background-color: #a3e9f4; /* Change background color on hover */
	  transform: translateY(-3px); /* Slightly lift the button on hover */
	}
  
	/* Active (pressed) effect */
	.submit-btn:active {
	  background-color: #163098; /* Darker color when button is pressed */
	  transform: translateY(0px); /* Return to original position when pressed */
	}
  
	/* Disabled state (optional) */
	.submit-btn:disabled {
	  background-color: #cccccc; /* Gray background for disabled state */
	  color: #666666; /* Gray text */
	  cursor: not-allowed; /* Disable pointer cursor */
	}
  </style>
  