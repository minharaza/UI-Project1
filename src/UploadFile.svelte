<!-- <script>
    let imageUrl = '';

    function handleFileSelect(event) {
        const file = event.target.files[0];
        if (file) {
            const reader = new FileReader();
            reader.onload = (e) => {
                imageUrl = e.target.result;
            };
            reader.readAsDataURL(file);
        }
    }
</script>

<div class="container">
    <label for="many">Upload the outfit for the day!</label> 
    <input type="file" accept="image/*" on:change={handleFileSelect}>

    {#if imageUrl}
        <img src={imageUrl} alt="Image preview">
    {/if}
</div>

taken from svelte.com-->

<!-- style>
    @import url('https://fonts.googleapis.com/css2?family=Matemasie&family=Ojuju:wght@200..800&family=Rubik+Bubbles&display=swap');
    .container {
        display: flex;
        flex-direction: column;
        align-items: center; /* Center the contents horizontally */
        justify-content: center; /* Center the contents vertically */
        text-align: center;
    }

    img {
        width: 300px; /* Specify a width for the image */
        margin-top: 20px; /* Add some space between the image and the button */
    }

    input[type="file"] {
        margin-top: 10px; /* Adds space between the upload button and the text */
    }

    label {
    font-family: "Ojuju", sans-serif;
    font-optical-sizing: auto;
    font-weight: 600;
    font-size: 20px;
    font-style: normal;
    margin-bottom: 1px;
    margin-top: 50px; /* Adds space above the label to move it down */
}

</style> --> 

<script>
    export let imageUrl = ''; // Bindable image URL to be sent to the parent component
  
    // Function to handle file selection and preview
    function handleFileSelect(event) {
      const file = event.target.files[0]; // Get the first file from the file input
      if (file) {
        const reader = new FileReader(); // Create a FileReader to read the file
        reader.onload = (e) => {
          imageUrl = e.target.result; // Set the imageUrl to the file's data URL (base64)
        };
        reader.readAsDataURL(file); // Read the file as a data URL
      }
    }
  </script>
  
  <div class="upload-container">
    <label for="file-upload">Upload your outfit image:</label>
    <input id="file-upload" type="file" accept="image/*" on:change={handleFileSelect} />
  
    <!-- Display the image preview if imageUrl is not empty -->
    {#if imageUrl}
      <img src={imageUrl} alt="Image preview" class="image-preview" />
    {/if}
  </div>
  
  <style>
    .upload-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      margin-bottom: 20px;
    }
  
    label {
      font-family: 'Ojuju', sans-serif;
      font-size: 20px;
      font-weight: 800;
      color: #dcf0ff; 
      margin-bottom: 10px;
    }
  
    input[type="file"] {
      padding: 10px;
      border-radius: 8px;
      border: 2px solid #fe009d;
      background-color: #ff9fda;
      font-size: 16px;
      cursor: pointer;
    }
  
    .image-preview {
      margin-top: 20px;
      width: 300px;
      border-radius: 10px;
      border: 2px solid #fe009d;
      box-shadow: #fe009d /* Subtle shadow for the image */
    }
  </style>
  
