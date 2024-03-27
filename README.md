# Esoft
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Home Visualization</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  
  <!-- Main Container -->
  <div class="home-container">
    
    <!-- House Base -->
    <div class="house-base"></div>

    <!-- Roof -->
    <div class="roof"></div>
  
    <!-- Window -->
    <div class="window"></div>
  
    <!-- Chimney -->
    <div class="chimney"></div>

  </div>
  
</body>
</html>

* {
  box-sizing: border-box;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  background-color: #f5f5dc; /* Light Goldenrod Yellow */
}

.home-container {
  position: relative;
  width: 400px;
  height: 267px; /* The ratio of the house is approximately 1.7391 */
}

/* House Base */
.house-base {
  position: absolute;
  bottom: 0;
  left: calc(50% - 100px);
  width: 200px;
  height: 150px;
  background-color: brown; /* Brown */
}

/* Roof */
.roof {
  position: absolute;
  top: 0;
  left: calc(50% - 125px);
  width: 0;
  height: 0;
  border-left: 125px solid transparent;
  border-right: 125px solid transparent;
  border-bottom: 125px solid orange; /* Orange */
}

/* Window */
.window {
  position: absolute;
  top: 60%;
  left: calc(50% - 25px);
  width: 50px;
  height: 50px;
  background-color: blue; /* Blue */
  border-radius: 50%;
}

/* Chimney */
.chimney {
  position: absolute;
  top: 50px;
  right: 100px;
  width: 20px;
  height: 50px;
  background-color: black; /* Black */
}

