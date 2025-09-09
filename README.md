# Anjuuuu-birthday-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Happy Birthday Anjuuu!</title>
  <style>
    body { margin:0; padding:0; overflow:hidden; background: #ffe6e6; display:flex; justify-content:center; align-items:center; height:100vh; flex-direction:column; font-family: 'Segoe UI', sans-serif; }
    h1 { font-size:3rem; color:#d63384; text-align:center; }
    p { font-size:1.5rem; color:#555; text-align:center; }
    canvas { position:absolute; top:0; left:0; }
  </style>
</head>
<body>
  <h1>Happy Birthday, Anjuuu! 🎂</h1>
  <p>You’re the best—always in my heart 💖</p>
  <canvas id="confetti"></canvas>
  <script>
    const canvas = document.getElementById('confetti');
    const ctx = canvas.getContext('2d');
    let W = canvas.width = window.innerWidth;
    let H = canvas.height = window.innerHeight;

    window.addEventListener('resize', () => {
      W = canvas.width = window.innerWidth;
      H = canvas.height = window.innerHeight;
    });

    const particles = [];
    const colors = ['#ff6b6b','#ffcd3c','#6b5b95','#88d8b0','#c34a36'];

    function initParticles() {
      for (let i = 0; i < 150; i++) {
        particles.push({
          x: Math.random() * W,
          y: Math.random() * H - H,
          r: Math.random() * 6 + 4,
          d: Math.random() * 40 + 10,
          color: colors[Math.floor(Math.random() * colors.length)],
          tilt: Math.floor(Math.random() * 10) - 10,
          tiltAngle: 0,
          tiltAngleIncrement: Math.random() * 0.07 + 0.05
        });
      }
    }

    function draw() {
      ctx.clearRect(0, 0, W, H);
      particles.forEach((p) => {
        ctx.beginPath();
        ctx.lineWidth = p.r;
        ctx.strokeStyle = p.color;
        ctx.moveTo(p.x + p.tilt + p.r / 2, p.y);
        ctx.lineTo(p.x + p.tilt, p.y + p.tilt + p.r / 2);
        ctx.stroke();
      });
      update();
    }

    function update() {
      particles.forEach((p, idx) => {
        p.tiltAngle += p.tiltAngleIncrement;
        p.y += (Math.cos(p.d) + 3 + p.r / 2) / 2;
        p.x += Math.sin(p.d);

        p.tilt = Math.sin(p.tiltAngle) * 15;

        if (p.y > H) {
          particles[idx] = {
            x: Math.random() * W,
            y: -20,
            r: p.r,
            d: p.d,
            color: p.color,
            tilt: p.tilt,
            tiltAngle: p.tiltAngle,
            tiltAngleIncrement: p.tiltAngleIncrement
          }
        }
      });
    }

    initParticles();
    (function animloop() {
      draw();
      requestAnimationFrame(animloop);
    })();
  </script>
</body>
</html>
