<!DOCTYPE html>
<html>
  <head>
    <title>Dnevnik beleški</title>
    <style>
      /* General styles */
      body {
        background-color: #ADD8E6; /* Light blue */
        font-family: Arial, sans-serif;
      }
      
      /* Form styles */
      form {
        background-color: #FFFFCC; /* Light yellow */
        padding: 20px;
        border-radius: 10px;
        box-shadow: 2px 2px 10px #888888;
      }
      
      /* Label styles */
      label {
        font-size: 1.2em;
        font-weight: bold;
        margin-right: 10px;
      }
      
      /* Input and textarea styles */
      input[type="date"], textarea {
        font-size: 1.1em;
        padding: 5px;
        border-radius: 5px;
        border: none;
        box-shadow: 1px 1px 5px #888888;
      }
      
      /* Submit button styles */
      input[type="submit"] {
        background-color: #000080; /* Dark blue */
        color: #FFFFFF; /* White */
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        font-size: 1.1em;
        font-weight: bold;
        cursor: pointer;
      }
      
      input[type="submit"]:hover {
        background-color: #FFFFFF; /* White */
        color: #000080; /* Dark blue */
      }
    </style>
  </head>
  <body>
    <h1>Dnevnik beleški</h1>
    <form id="dnevnik-forma">
      <label for="datum">Datum:</label>
      <input type="date" id="datum" name="datum">
      <br>
      <label for="beleška">Beleška:</label>
      <textarea id="beleška" name="beleška"></textarea>
      <br>
      <input type="submit" value="Upiši">
    </form>
    <div id="poruka"></div>
    
    <script>
      // Selektujemo formu
      const forma = document.querySelector("#dnevnik-forma");
      
      // Dodajemo event listener za submit forme
      forma.addEventListener("submit", proveriFormu);
      
      function proveriFormu(e) {
        // Selektujemo datum i belešku
        const datum = document.querySelector
