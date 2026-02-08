<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Do you love me?</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(135deg, #ff4d6d, #7b2ff7);
      font-family: Arial, sans-serif;
      color: white;
    }

    .box {
      background: rgba(255,255,255,0.15);
      padding: 30px;
      border-radius: 20px;
      text-align: center;
      backdrop-filter: blur(10px);
      width: 280px;
      position: relative;
    }

    h2 {
      margin-bottom: 20px;
    }

    button {
      padding: 10px 20px;
      border: none;
      border-radius: 25px;
      font-size: 16px;
      cursor: pointer;
      margin: 10px;
    }

    .yes {
      background: #00e676;
      color: black;
    }

    .no {
      background: #ff1744;
      color: white;
      position: absolute;
    }

    .result {
      display: none;
      margin-top: 20px;
      font-size: 18px;
    }

    #qrcode {
      margin-top: 20px;
    }
  </style>
</head>

<body>

  <div class="box">
    <h2>Do you love me? 💖</h2>

    <button class="yes" onclick="showLove()">Yes 😍</button>
    <button class="no" onmouseover="moveNo()">No 🙈</button>

    <div class="result" id="result">
      I knew it 😌💗
    </div>

    <!-- QR CODE HERE -->
    <div id="qrcode"></div>
  </div>

  <!-- QR CODE LIBRARY -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>

  <script>
    function showLove() {
      document.getElementById("result").style.display = "block";
    }

    function moveNo() {
      const btn = document.querySelector(".no");
      const box = document.querySelector(".box");

      const maxX = box.clientWidth - btn.offsetWidth;
      const maxY = box.clientHeight - btn.offsetHeight;

      btn.style.left = Math.random() * maxX + "px";
      btn.style.top = Math.random() * maxY + "px";
    }

    // CREATE QR CODE
    new QRCode(document.getElementById("qrcode"), {
      text: "https://your-website-link-here",
      width: 120,
      height: 120
    });
  </script>

</body>
</html># Dharshan-
A cute and fun “Do you love me?” webpage created using HTML, CSS, and JavaScript with an interactive QR code for sharing.
