<!-- <script>
	let a = 0;
	let b = 0;
    let F = 'Fahrenheit'; // Correct spelling
</script>

<div class="temperature-inputs">
    <p class="question">What was the temperature today? ({F})</p>

    <div class="input-section">
        <p class="label">Low?</p>
        <div class="input-group">
            <input id="Low" type="number" bind:value={a} min="-100" max="150" class="number-input" />
            <input type="range" bind:value={a} min="-100" max="150" class="range-slider" />
        </div>
    </div>

    <div class="input-section">
        <p class="label">High?</p>
        <div class="input-group">
            <input id="High" type="number" bind:value={b} min="-100" max="150" class="number-input" />
            <input type="range" bind:value={b} min="-100" max="150" class="range-slider" />
        </div>
    </div>

    <p class="result">Today was a low of {a} degrees {F} and a high of {b} degrees {F}</p>
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Matemasie&family=Ojuju:wght@200..800&family=Rubik+Bubbles&display=swap');
	
	/* body {
		font-family: "Ojuju", sans-serif;
		margin: 20px;
	} */

    .temperature-inputs {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 20px;
        border: 1px solid #d62cc8;
        border-radius: 10px;
        width: 80%;
        margin: auto;
        background-color: hsl(71, 60%, 66%);
    }

    .question {
		font-family: "Ojuju", sans-serif;
        color: rgb(159, 6, 186);
        font-weight: 600;
        font-size: 24px;
        margin-bottom: 20px;
        text-align: center;
    }

    .input-section {
		font-family: "Ojuju", sans-serif;
        color: rgb(159, 6, 186);
		font-weight: 600;
        margin-bottom: 20px;
        width: 100%;
    }

    .label {
        font-size: 20px;
        font-weight: 700;
        margin-bottom: 10px;
    }

    .input-group {
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 20px; /* Space between number input and range slider */
    }

    .number-input {
        width: 80px;
        padding: 5px;
        font-size: 16px;
        border-radius: 5px;
        border: 1px solid #d62cc8;
    }

    .range-slider {
        flex: 1;
        -webkit-appearance: none; /* Removes default styles for the slider */
        appearance: none;
        height: 8px;
        background: #d4a5ff;
        border-radius: 5px;
        outline: none;
    }

    .range-slider::-webkit-slider-thumb {
        -webkit-appearance: none;
        appearance: none;
        width: 20px;
        height: 20px;
        background: #fc77e6;
        cursor: pointer;
        border-radius: 50%;
    }

    .range-slider::-moz-range-thumb {
        width: 20px;
        height: 20px;
        background: #4CAF50;
        cursor: pointer;
        border-radius: 50%;
    }

    .result {
		font-family: "Ojuju", sans-serif;
        color: rgb(159, 6, 186);
		margin: 20px;
        font-size: 20px;
        font-weight: 600;
        text-align: center;
        margin-top: 20px;
    }
</style> -->


<script>
    export let lowTemp = '';  // Low temperature, bound to App.svelte
    export let highTemp = ''; // High temperature, bound to App.svelte
  </script>
  
  <div class="temperature-inputs">
    <p class="question">What was the temperature today?</p>
  
    <!-- Low temperature input -->
    <div class="input-section">
      <label for="low-temp">Low Temperature:</label>
      <div class="slider-container">
        <input id="low-temp" type="number" bind:value={lowTemp} min="-100" max="150" class="temp-input" />
        <input type="range" bind:value={lowTemp} min="-100" max="150" class="slider" />
      </div>
    </div>
  
    <!-- High temperature input -->
    <div class="input-section">
      <label for="high-temp">High Temperature:</label>
      <div class="slider-container">
        <input id="high-temp" type="number" bind:value={highTemp} min="-100" max="150" class="temp-input" />
        <input type="range" bind:value={highTemp} min="-100" max="150" class="slider" />
      </div>
    </div>
  
    <p class="result">Today was a low of {lowTemp}° and a high of {highTemp}°</p>
  </div>
  
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Matemasie&family=Rubik+Bubbles&display=swap');
  
    .temperature-inputs {
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 20px;
      border: 1px solid #d62cc8;
      border-radius: 10px;
      width: 100%;
      max-width: 600px;
      margin: 20px auto;
      background-color: hsl(71, 60%, 66%);
    }
  
    .question {
      font-family: 'Ojuju', sans-serif;
      font-weight: 800;
      font-size: 24px;
      color: rgb(159, 6, 186);
      margin-bottom: 20px;
      text-align: center;
    }
  
    .input-section {
      width: 100%;
      margin-bottom: 20px;
    }
  
    label {
      font-family: 'Ojuju', sans-serif;
      font-size: 18px;
      font-weight: 700;
      color: rgb(82, 93, 255);
      margin-bottom: 10px;
    }
  
    .slider-container {
      display: flex;
      gap: 10px;
      align-items: center;
    }
  
    .temp-input {
      width: 70px;
      padding: 8px;
      font-size: 16px;
      border-radius: 5px;
      border: 2px solid #fe009f;
      text-align: center;
    }
  
    .slider {
      flex: 1;
      -webkit-appearance: none;
      appearance: none;
      height: 8px;
      background-color: #f0f0f0;
      border-radius: 5px;
      outline: none;
    }
  
    .slider::-webkit-slider-thumb {
      -webkit-appearance: none;
      appearance: none;
      width: 20px;
      height: 20px;
      background-color: #fc77e6;
      border-radius: 50%;
      cursor: pointer;
    }
  
    .slider::-moz-range-thumb {
      width: 20px;
      height: 20px;
      background-color: #fc77e6;
      border-radius: 50%;
      cursor: pointer;
    }
  
    .result {
      font-family: 'Ojuju', sans-serif;
      font-weight: 800;
      color: #fe009f;
      font-size: 18px;
      font-weight: 600;
      margin-top: 10px;
    }
  </style>
  