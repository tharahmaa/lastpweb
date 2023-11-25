<template>
    <header class="masthead bg-gray-900 text-white full-page-header">
      <div class="container mx-auto p-8">
        <div class="text-2xl font-bold mb-2" style="font-family: 'Montserrat',">Nice To Meet You</div>
        <div class="text-4xl font-extrabold text-uppercase mb-4" style="font-family: 'Montserrat',">Welcome To Our Recipe Book!</div>
        <a href="#portfolio" class="custom-button" >
          Cari Resep
        </a>
      </div>
    </header>
  </template>
  
  <script>
  export default {
    // Component-specific options
  };
  </script>
  
  <style scoped>
  .full-page-header {
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  @font-face {
    font-family: 'Montserrat';
    src: url('/path/to/montserrat.woff2') format('woff2');
    font-weight: 400;
    font-style: normal;
  }

  .custom-button {
    display: inline-block;
    padding: 10px 20px;
    background-color: #C38154;
    color: #ffffff; 
    border-radius: 10px; 
    text-decoration: none;
    font-size: 16px;
    font-weight: bold;
    transition: background-color 0.3s ease-in-out;
  }

  .custom-button:hover {
    background-color: #F9E0BB; 
  }
  </style>
  