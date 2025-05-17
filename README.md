<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>RoboPavana</title>
  <style>
    body {
      margin: 0;
      background: #111;
      color: #fff;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      overflow: hidden;
    }

    .robot {
      width: 200px;
      height: 250px;
      background: #555;
      border-radius: 20px;
      box-shadow: 0 0 20px #0ff;
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

    .eye::after {
      content: '';
      width: 10px;
      height: 10px;
      background: #0ff;
      border-radius: 50%;
      position: absolute;
      top: 10px;
      left: 10px;
    }

    .eye.left {
      left: 40px;
    }

    .eye.right {
      right: 40px;
    }

    .mouth {
      width: 80px;
      height: 20px;
      background: #0ff;
      border-radius: 10px;
      position: absolute;
      bottom: 40px;
      left: 50%;
      transform: translateX(-50%);
    }

    .message {
      margin-top: 30px;
      font-size: 24px;
      animation: bounce 2s infinite ease-in-out;
    }

    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
  </style>
</head>
<body>
  <div class="robot">
    <div class="eye left" id="leftEye"></div>
    <div class="eye right" id="rightEye"></div>
    <div class="mouth"></div>
  </div>
  <div class="message">👋 Hi! Welcome!</div>

  <script>
    const leftEye = document.getElementById("leftEye");
    const rightEye = document.getElementById("rightEye");

    document.addEventListener("mousemove", (e) => {
      const x = (e.clientX - window.innerWidth / 2) / 50;
      const y = (e.clientY - window.innerHeight / 2) / 50;

      leftEye.style.transform = `translate(${x}px, ${y}px)`;
      rightEye.style.transform = `translate(${x}px, ${y}px)`;
    });
  </script>
</body>
</html>
