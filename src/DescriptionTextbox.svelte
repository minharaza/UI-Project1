<!-- <script>
	import { marked } from 'marked';
	let text = `Write a lil entry about this outfit today! Happy writing :)`;
	export let value = '';
</script>

<!-- <textarea bind:value={text} /> -->

<!-- textarea bind:value={value}></textarea> -->

<!-- Applying the 'text' class to the markdown content -->
<!-- div class="text">
    {@html marked(text)}
</div> -->

<!-- style>
	@import url('https://fonts.googleapis.com/css2?family=Matemasie&family=Ojuju:wght@200..800&family=Rubik+Bubbles&display=swap');
	
	textarea {
		width: 70%;
		height: 200px;
	}

	.text {
		font-family: "Ojuju", sans-serif;
		font-optical-sizing: auto;
		font-size: 25px;
		font-weight: 600; /* Define a specific font weight */
		font-style: normal;
	}
</style> --> 
<!-- script>
	export let value = 0; // This will bind the selected rating to the parent component
  
	// Function to handle when a user selects a rating
	function setRating(newRating) {
	  value = newRating;
	}
  </script> -->
  
  <!-- div class="stars-container">
	{#each Array(5) as _, index (index)}
	  Star buttons -->
	  <!-- span class="star" on:click={() => setRating(index + 1)}>
		{#if value > index}
		  //⭐ Filled star for selected ratings -->
		<!-- {:else}
		 // ☆ Empty star for unselected ratings -->
		<!-- ///if}
	  //span>
	/each} 
  </div>  -->
  
  <!-- style>
	.stars-container {
	  display: inline-block;
	  cursor: pointer;
	}
  
	.star {
	  font-size: 2rem;
	  color: gold;
	  padding: 5px;
	  transition: transform 0.2s;
	}
  
	.star:hover {
	  transform: scale(1.2); /* Slightly increase size on hover for effect */
	}
  </style> -->

  <script>
	export let value = ''; // Bindable value for the text area
  </script>
  
  <div class="textbox-container">
	<label for="description">Outfit Description:</label>
	<textarea
	  id="description"
	  bind:value={value}
	  placeholder="Write a description about your outfit..."
	></textarea>
  </div>
  
  <style>
	@import url('https://fonts.googleapis.com/css2?family=Matemasie&family=Rubik+Bubbles&display=swap');
  
	.textbox-container {
	  display: flex;
	  flex-direction: column;
	  width: 100%;
	  margin-bottom: 20px;
	}
  
	label {
	  font-family: 'Ojuju', sans-serif;
	  font-weight: 800;
	  font-size: 20px;
	  margin-bottom: 8px;
	  color: #dcf0ff; /* Purple color for label */
	}
  
	textarea {
	  font-family: 'Ojuju', sans-serif;
	  width: 100%;
	  height: 150px;
	  padding: 10px;
	  border-radius: 8px;
	  border: 2px solid #fe009d; /* Adds a border with your color choice */
	  font-size: 16px;
	  color: #333;
	  resize: none;
	  background-color: #ff9fda; /* Light background for better readability */
	  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1); /* Adds a subtle shadow */
	}
  
	textarea:focus {
	  outline: none;
	  border-color: #a30000; /* Change border color on focus */
	  box-shadow: 0px 0px 8px rgba(163, 0, 0, 0.5); /* Adds a glow on focus */
	}
  </style>
  
  
