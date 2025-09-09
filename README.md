<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Happy Birthday Anjuuu 🎂</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      text-align: center;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      overflow-x: hidden;
    }
    h1 {
      font-size: 3rem;
      color: #fff;
      margin-top: 50px;
      animation: fadeIn 2s ease-in-out;
    }
    p {
      font-size: 1.2rem;
      color: #fff;
      padding: 0 20px;
      animation: fadeIn 3s ease-in-out;
    }
    .heart {
      color: red;
      font-size: 2rem;
      animation: pulse 1s infinite;
    }
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.2); }
      100% { transform: scale(1); }
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    .balloons {
      position: absolute;
      top: 100vh;
      left: 50%;
      transform: translateX(-50%);
      font-size: 2rem;
      animation: float 8s linear infinite;
    }
    @keyframes float {
      0% { top: 100vh; opacity: 1; }
      100% { top: -10vh; opacity: 0; }
    }
    .footer {
      margin-top: 50px;
      font-size: 1rem;
      color: white;
      opacity: 0.8;
    }
  </style>
</head>
<body>
  <h1>🎉 Happy Birthday Anjuuu 🎉</h1>
  <p>Tere liye yeh din bahut special hai 💖<br>
     Tu meri best friend hai aur hamesha rahegi 🫂<br>
     Teri muskaan meri duniya roshan kar deti hai 😊<br>
     May all your dreams come true! 🌟</p>

  <div class="heart">❤️❤️❤️</div>

  <div class="footer">– From Your Best Friend, Jayant 🥰</div>

  <script>
    // Balloons create karne ke liye
    function createBalloon() {
      const balloon = document.createElement("div");
      balloon.classList.add("balloons");
      balloon.innerHTML = "🎈";
      balloon.style.left = Math.random() * window.innerWidth + "px";
      document.body.appendChild(balloon);

      setTimeout(() => {
        balloon.remove();
      }, 8000);
    }

    setInterval(createBalloon, 1000);
  </script>
</body>
</html>