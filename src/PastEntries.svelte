<!-- <script>
  // Sample hardcoded past entries data with image URLs
  export let oldEntries = [
    { 
      date: "09/18/2024", 
      paragraph: "This outfit features a vibrant floral off-shoulder top paired with casual, distressed denim shorts, creating a perfect balance of playful and relaxed summer vibes. The combination is ideal for warm weather outings, offering a chic yet laid-back look.", 
      rating: 4, 
      occasion: "Work", 
      imageUrl: "https://i.pinimg.com/736x/35/bb/b8/35bbb81ceb8308e7b873fa99eee4951b.jpg" // Replace with actual image path 
    },
    { 
      date: "09/17/2024", 
      paragraph: "This outfit showcases a sleek black jumpsuit with a deep V-neckline, exuding elegance and sophistication. The minimal design is both modern and chic, making it a versatile choice for formal events or a stylish evening out.", 
      rating: 5, 
      occasion: "Party", 
      imageUrl: "https://d2bzx2vuetkzse.cloudfront.net/fit-in/0x450/unshoppable_producs/9558cfa8-8383-4cda-bc02-188f236a783a.jpeg" // Replace with actual image path
    },
    { 
      date: "09/16/2024", 
      paragraph: "This outfit features a bright yellow kurta with intricate white embroidery, paired with white palazzo pants for a breezy, elegant look. The ensemble is complemented by a matching yellow dupatta, adding a touch of traditional grace to the vibrant, summery attire", 
      rating: 3, 
      occasion: "Errands", 
      imageUrl: "https://i.pinimg.com/736x/55/9a/d8/559ad84f501f8f541dd61dcb67b976ac.jpg" // Replace with actual image path
    }
  ];
</script>



<style>
  .past-entries {
    margin-top: 20px;
    padding: 10px;
    background-color: rgba(255, 255, 255, 0.8);
    border-radius: 10px;
  }

  .entry {
    margin-bottom: 15px;
    padding: 10px;
    border-bottom: 1px solid #ccc;
    display: flex;
    align-items: center;
  }

  .entry:last-child {
    border-bottom: none;
  }

  .entry-title {
    font-weight: bold;
    font-size: 18px;
    color: #333;
  }

  .entry-info {
    margin-left: 15px;
  }

  .entry img {
    max-width: 100px;
    max-height: 100px;
    border-radius: 5px;
  }

  .rating {
    color: gold;
  }
</style>

<div class="past-entries">
  <h2>Past Outfit Entries</h2>
  {#each oldEntries as entry}
    <div class="entry">
      <img src={entry.imageUrl} alt="Outfit image" />
      
      <div class="entry-info">
        <div class="entry-title">Date: {entry.date}</div>
        <p>Outfit: {entry.parapgraph}</p>
        <p>Occasion: {entry.occasion}</p>
        <p>Rating: 
          {#each { length: entry.rating } as _} 
            <span class="rating">⭐</span> 
          {/each}
        </p>
      </div>
    </div>
  {/each}
</div> -->

<script>
  // Accept an array of oldEntries from the parent component
  export let oldEntries = [];
</script>

<div class="past-entries">
  <h2>Past Outfit Entries</h2>

  {#if oldEntries.length === 0}
    <p>No entries yet. Add your first outfit entry!</p>
  {:else}
    {#each oldEntries as entry}
      <div class="entry">
        <div class="entry-image">
          <img src={entry.imageUrl} alt="Outfit Image" />
        </div>
        <div class="entry-details">
          <p><strong>Date:</strong> {entry.date}</p>
          <p><strong>Description:</strong> {entry.description}</p>
          <p><strong>Rating:</strong> 
            {#each Array(entry.rating) as _}
              <span>⭐</span>
            {/each}
          </p>
          {#if entry.selectedCenterChoices && entry.selectedCenterChoices.length > 0}
            <p><strong>Outfit Focus:</strong> {entry.selectedCenterChoices.join(', ')}</p>
          {/if}
          {#if entry.selectedWeather}
            <p><strong>Weather:</strong> {entry.selectedWeather}</p>
          {/if}
          {#if entry.wornAgain}
            <p><strong>Would Wear Again:</strong> {entry.wornAgain}</p>
          {/if}
          {#if entry.wornToPlaces && entry.wornToPlaces.length > 0}
            <p><strong>Worn To:</strong> {entry.wornToPlaces.join(', ')}</p>
          {/if}
          {#if entry.lowTemp || entry.highTemp}
            <p><strong>Temperature:</strong> Low of {entry.lowTemp}° and High of {entry.highTemp}°</p>
          {/if}
        </div>
      </div>
    {/each}
  {/if}
</div>

<style>
  .past-entries {
    margin-top: 40px;
    padding: 20px;
    background-color: rgba(255, 255, 255, 0.9);
    border-radius: 10px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
    max-width: 800px;
    margin-left: auto;
    margin-right: auto;
  }

  h2 {
    font-family: 'Ojuju', sans-serif;
    font-size: 24px;
    color: rgb(159, 6, 186);
    margin-bottom: 20px;
    text-align: center;
  }

  .entry {
    display: flex;
    margin-bottom: 20px;
    padding: 10px;
    border-bottom: 1px solid #ddd;
  }

  .entry:last-child {
    border-bottom: none;
  }

  .entry-image {
    margin-right: 20px;
  }

  .entry-image img {
    width: 100px;
    height: 100px;
    object-fit: cover;
    border-radius: 10px;
    border: 2px solid #b60000;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  }

  .entry-details {
    font-family: 'Ojuju', sans-serif;
    color: #333;
    font-size: 16px;
  }

  .entry-details p {
    margin: 5px 0;
  }

  .entry-details span {
    color: gold;
    font-size: 1.2rem;
  }
</style>
