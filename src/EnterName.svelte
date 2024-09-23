<!-- <script>
    let UserNameInput = '';
  </script>
  
  <div class="container">
    <input class="name-input" bind:value={UserNameInput} placeholder="What's your name?" />
    <p class="greeting">Hey {UserNameInput || 'cutie'}! <br /> Welcome to your outfit tracker.</p> <br />
  </div>
  
  
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Matemasie&family=Ojuju:wght@200..800&family=Rubik+Bubbles&display=swap');
    /* Full-height container to position content at the top center */
    .container {
      display: flex;
      flex-direction: column;
      justify-content: flex-start; /* Aligns content to the top */
      align-items: center; /* Centers content horizontally */
      height: 15vh; /* Full viewport height */
      padding-top: 10px; /* Adds some space from the top */
      text-align: center;
    }
  
    /* Styling for input */
    .name-input {
      padding: 5px;
      font-size: 18px;
      border: 2px solid #ccc;
      border-radius: 8px;
      margin-bottom: 1px;
    }
  
    /* Styling for the greeting */
    .greeting {
        color: #ffecb3;
        font-family: "Matemasie", sans-serif;
        font-weight: 400;
        font-style: normal;
        font-size: 35px;
    }
  </style> -->

  
  <script>
    let userName = ''; // Variable to bind user input
  </script>
  
  <div class="name-container">
    <input
      class="name-input"
      bind:value={userName}
      placeholder="Enter your name..."
    />
    <p class="greeting">Hey {userName || 'cutie'}! <br /> Welcome to your outfit tracker.</p>
  </div>
  
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Matemasie&family=Rubik+Bubbles&display=swap');
  
    .name-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-bottom: 20px;
    }
  
    .name-input {
      padding: 8px;
      border-radius: 5px;
      background-color: #ff9fda;
      border: 2px solid #fe009d;
      font-size: 18px;
      width: 80%;
      max-width: 300px;
      text-align: center;
      margin-bottom: 10px;
    }
  
    .greeting {
      font-family: 'Matemasie', sans-serif;
      font-size: 40px;
      color: rgb(255, 232, 100);
    }
  </style>
  