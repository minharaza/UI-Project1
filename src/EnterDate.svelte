<!-- <script>
    let currentTime;

    // Function to update the current time
    const updateTime = () => {
        const now = new Date();
        currentTime = now.toLocaleString(); // This gives you a localized date and time string
    };

    // Update the time every second
    setInterval(updateTime, 1000);

    // Initialize time on component load
    updateTime();

   
</script>

<main class="center-top"> <!-- Change class to any of the examples above -->
                    <!-- <h3>Current Date and Time</h3>
                    <p>{currentTime}</p>
                main -->

<!-- <style>
    @import url('https://fonts.googleapis.com/css2?family=Matemasie&family=Rubik+Bubbles&display=swap');
    .center-top {
        color: rgb(159, 6, 186);
        position: fixed;
        top: 0;
        left: 78%;
        transform: translateX(57%);
        padding: -1;
        font-family: "Ojuju", sans-serif;
        font-optical-sizing: auto;
        font-weight: 300;
        font-size: 20px;
        font-style: normal;
    }
style  -->


<script>
    export let value = ''; // Bindable date value
  
    // Function to update the current time
    const updateTime = () => {
      const now = new Date();
      value = now.toLocaleString(); // Localized date and time string
    };
  
    // Update the time every second
    setInterval(updateTime, 1000);
    updateTime();
  </script>
  
  <main class="date-container">
    <h3>Current Date and Time</h3>
    <p>{value}</p> <!-- Display the current date -->
  </main>
  
  <style>
        @import url('https://fonts.googleapis.com/css2?family=Ojuju:wght@200..800&display=swap');

    .date-container {
    color: rgb(159, 6, 186);
    position: fixed; /* Fix it to the viewport */
    top: 0;
    left: 88%; /* Position it from the left of the viewport */
    transform: translateX(-50%); /* Center horizontally relative to its own width */
    padding: 10px; /* Use a valid padding value */
    font-family: "Ojuju", sans-serif;
    font-optical-sizing: auto;
    font-weight: 300;
    font-size: 20px;
    font-style: normal;
}

  </style>
  