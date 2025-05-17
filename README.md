![MasterHead](https://cdna.artstation.com/p/assets/images/images/028/102/058/original/pixel-jeff-matrix-s.gif?1593487263)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Pavana’s Robot</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      background: linear-gradient(to bottom, #0f2027, #203a43, #2c5364);
      font-family: Arial, sans-serif;
      color: #fff;
    }
    .robot {
      width: 200px;
      height: 250px;
      background: #4d4d4d;
      border-radius: 20px;
      box-shadow: 0 0 15px #00ffe1;
      position: relative;
    }
    .eye {
      width: 30px;
      height: 30px;
      background: black;
      border-radius: 50%;
      position: absolute;
      top: 60px;
    }
    .eye.left { left: 45px; }
    .eye.right { right: 45px; }
    .eye::after {
      content: '';
      position: absolute;
      width: 10px;
      height: 10px;
      background: #00ffff;
      border-radius: 50%;
      top: 10px;
      left: 10px;
    }
    .mouth {
      width: 80px;
      height: 20px;
      background: #00ffee;
      border-radius: 10px;
      position: absolute;
      bottom: 40px;
      left: 50%;
      transform: translateX(-50%);
    }
    .message {
      margin-top: 30px;
      font-size: 24px;
      animation: wave 2s infinite;
    }
    @keyframes wave {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-5px); }
    }
  </style>
</head>
<body>
  <div class="robot" id="robot">
    <div class="eye left" id="leftEye"></div>
    <div class="eye right" id="rightEye"></div>
    <div class="mouth"></div>
  </div>
  <div class="message">👋 Hi there! Welcome, I'm RoboPavana!</div>

  <script>
    const leftEye = document.getElementById('leftEye');
    const rightEye = document.getElementById('rightEye');

    document.addEventListener('mousemove', (e) => {
      const centerX = window.innerWidth / 2;
      const centerY = window.innerHeight / 2;
      const offsetX = (e.clientX - centerX) / 50;
      const offsetY = (e.clientY - centerY) / 50;

      leftEye.style.transform = `translate(${offsetX}px, ${offsetY}px)`;
      rightEye.style.transform = `translate(${offsetX}px, ${offsetY}px)`;
    });
  </script>
</body>
</html>
