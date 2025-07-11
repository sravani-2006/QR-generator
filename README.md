<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>QR Code Generator</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      font-family: 'Poppins', 'sans-serif';
      box-sizing: border-box;
    }

    body {
      background: rgb(255, 248, 235);
    }

    .container {
      background: #fff;
      width: 400px;
      padding: 25px 35px;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      border-radius: 10px;
    }

    .container p {
      font-weight: 600;
      font-size: 15px;
      margin-bottom: 8px;
    }

    .container input {
      padding: 10px;
      width: 100%;
      border: 1px solid #494eea;
      outline: 0;
      margin: 10px 0 20px;
      border-radius: 5px;
    }

    .container button {
      width: 100%;
      height: 50px;
      color: #fff;
      background: #494eea;
      border-radius: 15px;
      border: 0;
      outline: 0;
      box-shadow: 0 10px 10px rgba(0, 0, 0, 0.1);
      cursor: pointer;
      margin: 20px 0;
      font-weight: 500;
    }

    #imgbox {
      text-align: center;
      margin-top: 20px;
    }

    #imgbox img {
      width: 200px;
      border-radius: 5px;
    }
  </style>
</head>
<body>
  <div class="container">
    <p>Enter your text or URL</p>
    <input type="text" id="qrText" placeholder="Text or URL" />
    <button onclick="generateQR()">Generate QR Code</button>
    <div id="imgbox">
      <img id="qrImage" src="" alt="QR Code" />
    </div>
  </div>

  <script>
    function generateQR() {
      const input = document.getElementById("qrText").value.trim();
      const qrImage = document.getElementById("qrImage");
      const imgBox = document.getElementById("imgbox");

      if (input === "") {
        alert("Please enter some text or URL");
        return;
      }

      qrImage.src = "https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=" + encodeURIComponent(input);
      imgBox.style.display = "block";
    }
  </script>
</body>
</html>

