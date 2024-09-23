<script>
  import { onMount } from "svelte";
  import EnterName from './EnterName.svelte';
  import EnterDate from './EnterDate.svelte';
  import DescriptionTextbox from './DescriptionTextbox.svelte';
  import OutfitCenterChoice from './OutfitCenterChoice.svelte';
  import RankingStars from "./RankingStars.svelte";
  import UploadFile from "./UploadFile.svelte";
  import WeatherChoice from './WeatherChoice.svelte';
  import OutfitWornTo from './OutfitWornTo.svelte';
  import TemperatureRating from './TemperatureRating.svelte';
  import SubmitButton from "./SubmitButton.svelte";
  import PastEntries from "./PastEntries.svelte";

  let imageUrl = 'https://i.pinimg.com/564x/47/87/e3/4787e32ef9ff242b586a69ca832c86e9.jpg';

  // Variables for form data
  let entryDate = '';
  let description = '';
  let rating = 0;
  let imageUrlInput = '';
  let selectedCenterChoices = [];
  let selectedWeather = '';
  let wornAgain = '';
  let wornToPlaces = [];
  let lowTemp = '';
  let highTemp = '';
  let oldEntries = [];

  // Store the calculated height
  let translucentHeight = '1000px'; // Default initial value

  // Function to handle form submission
  function handleSubmit() {
    const newEntry = {
      date: entryDate,
      description: description,
      rating: rating,
      imageUrl: imageUrlInput,
      selectedCenterChoices: [...selectedCenterChoices],
      selectedWeather: selectedWeather,
      wornAgain: wornAgain,
      wornToPlaces: [...wornToPlaces],
      lowTemp: lowTemp,
      highTemp: highTemp
    };

    oldEntries = [...oldEntries, newEntry]; // Save the entry

    // Reset form values
    entryDate = '';
    description = '';
    rating = 0;
    imageUrlInput = '';
    selectedCenterChoices = [];
    selectedWeather = '';
    wornAgain = '';
    wornToPlaces = [];
    lowTemp = '';
    highTemp = '';

    // Trigger recalculation of content height after new entry
    updateHeight();
  }

  // Function to calculate and update the height of the translucent-rectangle dynamically
  function updateHeight() {
    const content = document.querySelector('.content'); // Select the content container
    if (content) {
      translucentHeight = `${content.offsetHeight + 200}px`; // Adding some padding
    }
  }

  // Recalculate the height after the page is rendered
  onMount(() => {
    updateHeight();
  });
</script>

<img class="full-screen-image" src="{imageUrl}" alt="Full Screen Image" />

<div class="translucent-rectangle" style="height: {translucentHeight};"></div>

<!-- Form and past entries content -->
<div class="content">
  <div class="container">
    <EnterName />
    <EnterDate bind:value={entryDate} />
    <UploadFile bind:imageUrl={imageUrlInput} />
    <RankingStars bind:value={rating} />
    <DescriptionTextbox bind:value={description} />
    <OutfitCenterChoice bind:selectedChoices={selectedCenterChoices} />
    <WeatherChoice bind:selectedWeather={selectedWeather} />
    <TemperatureRating bind:lowTemp={lowTemp} bind:highTemp={highTemp} />
    <OutfitWornTo bind:wornAgain={wornAgain} bind:wornToPlaces={wornToPlaces} />
    <SubmitButton on:click={handleSubmit} />
    <PastEntries {oldEntries} />
  </div>
</div>

<style>
  /* Full screen background image */
  .full-screen-image {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    object-fit: cover;
    object-position: center;
    z-index: -2;
  }

  /* Translucent rectangle */
  .translucent-rectangle {
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 1000px;
    background-color: rgba(172, 53, 132, 0.5);
    z-index: -1;
    border-radius: 10px;
    transition: height 0.3s ease; /* Smooth transition when height changes */
  }

  /* Form Components Container */
  .container {
    position: relative;
    z-index: 1;
    display: flex;
    flex-direction: column;
    gap: 20px;
    padding: 20px;
    align-items: center;
  }

  /* Content container (for height calculation) */
  .content {
    position: relative;
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>
