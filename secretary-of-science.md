<!DOCTYPE html>
<html>
<head>
  <title>Secretary of Science (Research)</title>
    <style>
       <link rel="stylesheet" type="text/css" href="styles.css">
    </style>
</head>
<body>
  <h1>Secretary of Science</h1>
  <p>(Research)</p>
  
  <h2>Choose a Time Slot you would like to assign the Secretary of Science to yourself</h2>
  <p>Please choose a Time Slot:</p>
  
  <div class="carousel">
    <select id="timeSlot">
      <option value="slot1">Time Slot 1</option>
      <option value="slot2">Time Slot 2</option>
      <option value="slot3">Time Slot 3</option>
      <!-- Add more time slot options as needed -->
    </select>
  </div>
  
  <div class="input-group">
    <label for="username">In Game Username:</label>
    <input type="text" id="username" required>
  </div>
  
  <div class="input-group">
    <label for="coordinateX">In Game Coordinates:</label>
    <input type="text" id="coordinateX" placeholder="X: ___" required>
    <input type="text" id="coordinateY" placeholder="Y: ___" required>
  </div>
  
  <div class="input-group">
    <label for="allianceTag">Alliance Tag:</label>
    <input type="text" id="allianceTag" maxlength="3" required>
  </div>
  
  <div class="buttons">
    <button onclick="clearForm()">Clear</button>
    <button onclick="submitForm()">Submit</button>
  </div>
  
  <div id="confirmationEmbed" class="confirmation-embed" style="display: none;">
    <h2>Secretary of Science</h2>
    <p id="selectedSlot"></p>
    <p id="usernameDisplay"></p>
    <p id="coordinatesDisplay"></p>
    <p id="allianceTagDisplay"></p>
    <p id="timestamp"></p>
    <p>Would you like to Download this Ticket?</p>
    <button class="download-button" onclick="downloadTicket()">Download</button>
  </div>
  
  <script>
    function clearForm() {
      document.getElementById("username").value = "";
      document.getElementById("coordinateX").value = "";
      document.getElementById("coordinateY").value = "";
      document.getElementById("allianceTag").value = "";
    }
    
    function submitForm() {
      var username = document.getElementById("username").value;
      var coordinateX = document.getElementById("coordinateX").value;
      var coordinateY = document.getElementById("coordinateY").value;
      var allianceTag = document.getElementById("allianceTag").value;
      
      if (username && coordinateX && coordinateY && allianceTag) {
        var timeSlot = document.getElementById("timeSlot");
        var selectedSlot = timeSlot.options[timeSlot.selectedIndex].text;
        
        document.getElementById("selectedSlot").textContent = "Time Slot Chosen: " + selectedSlot;
        document.getElementById("usernameDisplay").textContent = "Username: " + username;
        document.getElementById("coordinatesDisplay").textContent = "Coordinates: X: " + coordinateX + ", Y: " + coordinateY;
        document.getElementById("allianceTagDisplay").textContent = "Alliance Tag: " + allianceTag;
        document.getElementById("timestamp").textContent = "Timestamp: " + getCurrentDateTime();
        
        document.getElementById("confirmationEmbed").style.display = "block";
        
        // Remove the selected time slot from the carousel
        timeSlot.remove(timeSlot.selectedIndex);
      }
    }
    
    function getCurrentDateTime() {
      var currentDate = new Date();
      var dateTime = currentDate.toLocaleString();
      return dateTime;
    }
    
    function downloadTicket() {
      // Implement the logic to generate and download the ticket file
      alert("Download functionality not implemented yet.");
    }
  </script>
</body>
</html>
