<!-- <script>
  let CenterChoices = [
    'Makeup💄 ',
    'Top👚 ',
    'Bottoms👖 ',
    'Dress👗 ',
    'Jacket🧥 ',
    'Shoes👠 ',
    'Bag👜 ',
    'Accessories👓 ',
    'Hair 💇‍♀️' ,
    'Weather🌦️ '
  ];

  let selectedChoices = []; 

  function join(arr) {
    if (arr.length === 1) return arr[0];
    return `${arr.slice(0, -1).join(', ')} and ${arr[arr.length - 1]}`;
  }
</script>

<div class="outfit-container">
<p class="question">Outfit revolves around...?</p>

<div class="choices-container">
  {#each CenterChoices as Center}
    <label class="choice-label">
      <input type="checkbox" bind:group={selectedChoices} value={Center} class="checkbox"/>
      {Center}
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
@import url('https://fonts.googleapis.com/css2?family=Matemasie&family=Ojuju:wght@200..800&family=Rubik+Bubbles&display=swap');

.outfit-container {
  width: 80%;
  margin: 20px auto;
  padding: 20px;
  background-color: #a5e1ff;
  border: 1px solid #b60000;
  border-radius: 10px;
}

.question {
  font-family: 'Ojuju', sans-serif;
  color: #333333;
  font-weight: 600;
  font-size: 20px;
  margin-bottom: 10px;
}

.choices-container {
  display: flex;
  flex-wrap: wrap; /* Allows the labels to wrap neatly */
  gap: 15px; /* Adds space between checkboxes */
  margin-bottom: 20px;
}

.choice-label {
  font-family: 'Ojuju', sans-serif;
  color: #333333;
  display: flex;
  align-items: center;
  font-size: 16px;
  cursor: pointer;
}

.checkbox {
  font-family: 'Ojuju', sans-serif;
  color: #333333;
  margin-right: 10px;
  width: 18px;
  height: 18px;
}

.warning {
  color: rgb(242, 110, 209);
  font-family: 'Ojuju', sans-serif;
  font-weight: 700;
  font-size: 18px;
}

.selected {
  font-family: 'Ojuju', sans-serif;
  color: #333333;
  font-size: 18px;
  font-weight: 500;
  margin-top: 10px;
}
</style> -->


<script>
  export let selectedChoices = []; // Export selectedChoices to be bound to the parent

  let CenterChoices = [
    'Makeup💄 ',
    'Top👚 ',
    'Bottoms👖 ',
    'Dress👗 ',
    'Jacket🧥 ',
    'Shoes👠 ',
    'Bag👜 ',
    'Accessories👓 ',
    'Hair 💇‍♀️',
    'Weather🌦️ '
  ];

  // Function to join selected choices for display
  function join(arr) {
    if (arr.length === 1) return arr[0];
    return `${arr.slice(0, -1).join(', ')} and ${arr[arr.length - 1]}`;
  }
</script>

<div class="outfit-center-container">
  <p class="question">What does the outfit revolve around?</p>

  <div class="choices-container">
    {#each CenterChoices as Center}
      <label class="choice-label">
        <input type="checkbox" bind:group={selectedChoices} value={Center} class="checkbox" />
        {Center}
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
  @import url('https://fonts.googleapis.com/css2?family=Matemasie&family=Rubik+Bubbles&display=swap');

  .outfit-center-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    max-width: 600px;
    padding: 20px;
    margin-bottom: 20px;
    background-color: #ff9fda; /* Light translucent background */
    border-color: #fe009d;
    border-radius: 10px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1); /* Subtle shadow */
  }

  .question {
    font-family: 'Ojuju', sans-serif;
    font-size: 22px;
    font-weight: 800;
    color: #dcf0ff; 
    margin-bottom: 15px;
    text-align: center;
  }

  .choices-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 15px;
  }

  .choice-label {
    font-family: 'Ojuju', sans-serif;
    font-weight: 800;
    color: #fe009f;
    font-size: 18px;
    display: flex;
    align-items: center;
    cursor: pointer;
    background-color: #f0f0f0;
    padding: 8px 15px;
    border-radius: 8px;
    transition: background-color 0.2s;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  }

  .choice-label:hover {
    background-color: #e0d7ff; /* Lighter hover color */
  }

  .checkbox {
    margin-right: 10px;
    width: 20px;
    height: 20px;
    accent-color: rgb(159, 6, 186); /* Matches the purple theme */
  }

  .warning {
    color: rgb(82, 93, 255);
    font-family: 'Ojuju', sans-serif;
    font-weight: 700;
    font-size: 18px;
    margin-top: 15px;
  }

  .selected {
    font-family: 'Ojuju', sans-serif;
    color: #333333;
    font-size: 18px;
    margin-top: 15px;
    text-align: center;
  }
</style>
