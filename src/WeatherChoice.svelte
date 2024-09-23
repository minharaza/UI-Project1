<!-- <script>
  let WeatherChoices = ['☀️', '☁️', '⛅️', '☔️', '⚡️', '❄️'];
  let selectedChoices = []; 

  function join(arr) {
    if (arr.length === 1) return arr[0];
    return `${arr.slice(0, -1).join(', ')} and ${arr[arr.length - 1]}`;
  }
</script>

<div class="weather-container">
  <p class="question">What's the weather like?</p>

  <div class="weather-choices">
      {#each WeatherChoices as Chosen}
          <label class="weather-label">
              <input type="checkbox" bind:group={selectedChoices} value={Chosen} class="weather-checkbox" />
              <span class="emoji">{Chosen}</span>
          </label>
      {/each}
  </div>

  {#if selectedChoices.length === 0}
      <p class="warning">Please select at least one</p>
  {/if}

  {#if selectedChoices.length > 0}
      <p class="selected">Selected: {join(selectedChoices)}</p>
  {/if}
</div>

<style>
  .weather-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 20px;
      border: 1px solid #ddd;
      border-radius: 10px;
      background-color: #f6a878;
      width: 80%;
      margin: auto;
  }

  .question {
      font-family: 'Ojuju', sans-serif;
      font-size: 20px;
      font-weight: 700;
      margin-bottom: 15px;
  }

  .weather-choices {
      display: flex;
      justify-content: space-around;
      flex-wrap: wrap;
      gap: 20px; /* Spacing between weather options */
  }

  .weather-label {
      display: flex;
      align-items: center;
      font-size: 24px; /* Size of the emoji */
      cursor: pointer;
      gap: 10px;
  }

  .weather-checkbox {
      width: 24px;
      height: 24px;
      cursor: pointer;
  }

  .emoji {
      font-size: 28px; /* Makes the emoji larger */
  }

  .warning {
    color: rgb(242, 110, 209);
    font-family: 'Ojuju', sans-serif;
    font-weight: 700;
    font-size: 18px;
  }

  .selected {
      margin-top: 20px;
      font-size: 18px;
      font-weight: 500;
  }
</style> -->
<script>
    export let selectedWeather = ''; // This will be bound to App.svelte
  
    // Options for the weather selection
    let weatherOptions = ['Sunny ☀️', 'Cloudy ☁️', 'Rainy 🌧️', 'Snowy ❄️', 'Windy 💨', 'Foggy 🌫️'];
  </script>
  
  <div class="weather-choice-container">
    <p class="question">What was the weather like?</p>
    <select bind:value={selectedWeather} class="weather-dropdown">
      <option value="" disabled selected>Select weather</option>
      {#each weatherOptions as weather}
        <option value={weather}>{weather}</option>
      {/each}
    </select>
  </div>
  
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Matemasie&family=Rubik+Bubbles&display=swap');
  
    .weather-choice-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 100%;
      max-width: 500px;
      margin-bottom: 20px;
      padding: 10px;
      background-color: #c4d9f8; /* Light translucent background */
      border-radius: 10px;
      box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1); /* Subtle shadow */
    }
  
    .question {
      font-family: 'Ojuju', sans-serif;
      font-weight: 800;
      font-size: 20px;
      color: rgb(159, 6, 186); /* Purple color */
      margin-bottom: 10px;
    }
  
    .weather-dropdown {
      font-family: 'Ojuju', sans-serif;
      font-weight: 700;
      padding: 10px;
      border-radius: 8px;
      border: 2px solid rgb(82, 93, 255);
      font-size: 16px;
      background-color: #ff9fda;
      width: 100%;
      max-width: 400px;
    }
  
    .weather-dropdown:focus {
      outline: none;
      border-color: #fe009f;
    }
  </style>
  