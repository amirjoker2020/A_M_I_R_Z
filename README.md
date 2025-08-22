
<!DOCTYPE html>
<html lang="fa">
<head>
  <meta charset="UTF-8">
  <title>هک سیستم</title>
  <style>
    body {
      background-color: black;
      color: #00FF00;
      font-family: monospace;
      white-space: pre;
      margin: 0;
      padding: 0;
    }
    #id {@A_M_I_R_Z
      display: none;
      text-align: center;
      margin-top: 20%;
      font-size: 2em;
    }
  </style>
</head>
<body>
  <div id="matrix"></div>
  <div id="id">@YourID</div>

  <script>
    const matrix = document.getElementById('matrix');
    const id = document.getElementById('id');
    const chars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789@#$%^&*()*&^%';
    const width = 80;
    const height = 25;

    function getRandomChar() {
      return chars.charAt(Math.floor(Math.random() * chars.length));
    }

    function generateMatrixLine() {
      let line = '';
      for (let i = 0; i < width; i++) {
        line += getRandomChar();
      }
      return line;
    }

    function updateMatrix() {
      let text = '';
      for (let i = 0; i < height; i++) {
        text += generateMatrixLine() + '\n';
      }
      matrix.textContent = text;
    }

    let matrixInterval = setInterval(updateMatrix, 50);

    setTimeout(() => {
      clearInterval(matrixInterval);
      matrix.style.display = 'none';
      id.style.display = 'block';
    }, 5000);
  </script>
</body>
</html>
