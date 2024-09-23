<!-- <script>
	let answer = 1;
	let Places = ['School'];
	let SpecialOccasion = '';

	let AllPlaces = ['School', 'Work', 'Party', 'Errands', 'Special Event'];

	function join(Places) {
		if (Places.length === 1) return Places[0];
		return `${Places.slice(0, -1).join(', ')} and ${Places[Places.length - 1]}`;
	}
</script>

<div class="container">
	 Left Side - Radio buttons -->
	<!-- <div class="radio-column">
		<h3>Would wear again?</h3>

		<div class="radio-group">
			<label>
				Totally! It Slays!!!
				<input type="radio" bind:group={answer} value={1} />
			</label>

			<label>
				Maybe, but needs some tweaks...
				<input type="radio" bind:group={answer} value={2} />
			</label>

			<label>
				No...was a flop.
				<input type="radio" bind:group={answer} value={3} />
			</label>
		</div>
	</div>

	
	<div class="dropdown-column">
		<h3>Where did you wear this?</h3>

		<select class="places-select" multiple bind:value={Places}>
			{#each AllPlaces as flavour}
				<option value={flavour}>
					{flavour}
				</option>
			{/each}
		</select>

		<div class="response">
			{#if Places.includes('School')}
				<p>Slaying and Studious!</p>
			{:else if Places.includes('Work')}
				<p>Corporate Queen!</p>
			{:else if Places.includes('Party')}
				<p>365 Party Girl! #BRATSUMMER</p>
			{:else if Places.includes('Errands')}
				<p>Workin or Werkin?</p>
			{:else if Places.includes('Special Event')}
				<p>The world is your fashion show!</p>
			{/if}
		</div>
	</div>
</div>

<style>
	/* General styling */
	body {
		font-family: 'Ojuju', sans-serif;
		color: #333;
		margin: 0;
		padding: 0;
		background-color: #f9f9f9;
	}

	h3 {
		font-family: 'Ojuju', sans-serif;
		font-size: 22px;
		color: #5c67a3;
		margin-bottom: 15px;
	}

	/* Container for the two columns */
	.container {
		display: flex;
		justify-content: space-between;
		align-items: flex-start;
		width: 100%;
		max-width: 1000px;
		margin: 20px auto;
	}

	/* Left column for radio buttons */
	.radio-column {
		flex: 1;
		display: flex;
		flex-direction: column;
		align-items: flex-start; /* Align items to the left */
	}

	/* Radio button group styling */
	.radio-group {
		display: flex;
		flex-direction: column;
	}

	label {
		display: flex;
		align-items: center;
		font-family: 'Ojuju', sans-serif;
		font-size: 18px;
		font-weight: 700;
		margin-bottom: 10px;
		cursor: pointer;
		width: 100%;
		justify-content: space-between; /* Align text and radio button */
	}

	input[type="radio"] {
		margin-left: 10px;
		transform: scale(1.2); /* Makes the radio buttons bigger */
	}

	/* Right column for the dropdown */
	.dropdown-column {
		flex: 1;
		display: flex;
		flex-direction: column;
		align-items: flex-end; /* Align items to the right */
	}

	.places-select {
		width: 100%;
		max-width: 300px;
		padding: 10px;
		font-family: 'Ojuju', sans-serif;
		font-weight: bold;
		font-size: 16px;
		border-radius: 5px;
		border: 1px solid #ccc;
		background-color: #f5a0d6;
		margin-bottom: 20px;
	}

	.response p {
		font-family: 'Ojuju', sans-serif;
		font-size: 18px;
		color: #ffffff;
		font-weight: bold;
		margin-top: 10px;
		text-align: right;
	}

</style> --> 

<script>
	export let wornAgain = ''; // Whether the outfit will be worn again
	export let wornToPlaces = []; // Places where the outfit was worn
  
	let allPlaces = ['School', 'Work', 'Party', 'Errands', 'Special Event']; // Available places
  
	function join(places) {
	  if (places.length === 1) return places[0];
	  return `${places.slice(0, -1).join(', ')} and ${places[places.length - 1]}`;
	}
  </script>
  
  <div class="outfit-worn-to-container">
	<!-- Worn again radio buttons -->
	<h3>Would wear again?</h3>
	<div class="radio-group">
	  <label>
		<input type="radio" bind:group={wornAgain} value="Yes" />
		Totally! It Slays!!!
	  </label>
	  <label>
		<input type="radio" bind:group={wornAgain} value="Maybe" />
		Maybe, but needs some tweaks...
	  </label>
	  <label>
		<input type="radio" bind:group={wornAgain} value="No" />
		No...was a flop.
	  </label>
	</div>
  
	<!-- <div class="response">
		{#if Places.includes('School')}
			<p>Slaying and Studious!</p>
		{:else if Places.includes('Work')}
			<p>Corporate Queen!</p>
		{:else if Places.includes('Party')}
			<p>365 Party Girl! #BRATSUMMER</p>
		{:else if Places.includes('Errands')}
			<p>Workin or Werkin?</p>
		{:else if Places.includes('Special Event')}
			<p>The world is your fashion show!</p>
		{/if}
	</div> -->





	<!-- Worn to places dropdown -->
	<h3>Where did you wear this?</h3>
	<select multiple bind:value={wornToPlaces}>
	  {#each allPlaces as place}
		<option value={place}>{place}</option>
	  {/each}
	</select>
  
	<!-- Display selection -->

	  	{#if wornToPlaces.includes('School')}
	  	<p>Slaying and Studious!</p>
		{:else if wornToPlaces.includes('Work')}
			<p>Corporate Queen!</p>
		{:else if wornToPlaces.includes('Party')}
			<p>365 Party Girl! #BRATSUMMER</p>
		{:else if wornToPlaces.includes('Errands')}
			<p>Workin or Werkin?</p>
		{:else if wornToPlaces.includes('Special Event')}
			<p>The world is your fashion show!</p>

		{/if}
  </div>
  
  <style>
	@import url('https://fonts.googleapis.com/css2?family=Matemasie&family=Rubik+Bubbles&display=swap');
  
	.outfit-worn-to-container {
	  display: flex;
	  flex-direction: column;
	  align-items: flex-start;
	  width: 100%;
	  max-width: 600px;
	  padding: 20px;
	  margin-bottom: 20px;
	  background-color: #c4d9f8;
	  border-radius: 10px;
	  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
	}
  
	h3 {
	  font-family: 'Ojuju', sans-serif;
	  font-size: 22px;
	  color: rgb(159, 6, 186);
	  margin-bottom: 10px;
	}
  
	.radio-group {
	  display: flex;
	  flex-direction: column;
	  margin-bottom: 20px;
	}
  
	label {
	  font-family: 'Ojuju', sans-serif;
	  font-size: 18px;
	  margin-bottom: 10px;
	  cursor: pointer;
	}
  
	select {
	  font-family: 'Ojuju', sans-serif;
	  padding: 10px;
	  border-radius: 8px;
	  border: 2px solid #fe009f;
	  background-color: #fff7f0;
	  font-size: 20px;
	  margin-bottom: 10px;
	}
  
	p {
	  font-family: 'Ojuju', sans-serif;
	  font-weight: 600;
	  color: #333333;
	  font-size: 18px;
	  margin-top: 10px;
	}
  </style>
  