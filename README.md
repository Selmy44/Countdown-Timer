# Countdown-Timer
this is a Countdown Timer web
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Countdown Timer</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 50px;
    }

    #countdown {
      font-size: 24px;
      font-weight: bold;
      color: #333;
    }
  </style>
</head>
<body>

<div id="countdown">00:00:00</div>

<script>
  function startCountdown(durationInSeconds) {
    const countdownElement = document.getElementById('countdown');
    let timeRemaining = durationInSeconds;

    function updateCountdown() {
      const hours = Math.floor(timeRemaining / 3600);
      const minutes = Math.floor((timeRemaining % 3600) / 60);
      const seconds = timeRemaining % 60;

      const formattedTime = `${String(hours).padStart(2, '0')}:${String(minutes).padStart(2, '0')}:${String(seconds).padStart(2, '0')}`;
      countdownElement.textContent = formattedTime;

      if (timeRemaining <= 0) {
        clearInterval(intervalId);
        countdownElement.textContent = 'Time\'s up!';
      } else {
        timeRemaining--;
      }
    }

    updateCountdown(); // Initial call to display the initial value

    const intervalId = setInterval(updateCountdown, 1000); // Update every second
  }

  // Set the duration in seconds
  const durationInSeconds = 300; // 5 minutes
  startCountdown(durationInSeconds);
</script>

</body>
</html>
