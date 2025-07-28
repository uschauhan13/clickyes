<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Pooja ji, will you be mine? 💖</title>
  <style>
    body {
      text-align: center;
      font-family: 'Comic Sans MS', cursive;
      margin-top: 100px;
      background-color: #fff0f5;
    }
    h1 {
      color: #d63384;
    }
    button {
      padding: 15px 25px;
      margin: 20px;
      font-size: 20px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: 0.3s ease;
    }
    #yes {
      background-color: #28a745;
      color: white;
    }
    #no {
      background-color: #dc3545;
      color: white;
      position: relative;
    }
  </style>
</head>
<body>
  <h1>Pooja ji, will you be mine? 🥺❤</h1>
  <button id="yes">Yes 😍</button>
  <button id="no">No 🙈</button>
  <div id="message"></div>

  <script>
    const yesBtn = document.getElementById('yes');
    const noBtn = document.getElementById('no');
    const message = document.getElementById('message');

    const noMessages = [
      "Soch lo... 😏",
      "Ek baar aur soch lo 🥹",
      "Itni bhi jaldi kya hai? 🤭",
      "Bas karo, maan bhi jao 💖"
    ];

    let noClickCount = 0;

    yesBtn.addEventListener('click', () => {
      document.body.innerHTML = `
        <div style="text-align:center; padding-top:100px;">
          <h1>Finally! I knew it, Pooja ji ❤</h1>
          <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExdHZ4aDJyaDNybDdteGwwNGJ4a2Q3cmIybDh2OWF2ZmZ3bmFzcDZpZCZlcD12MV8y/g9582DNuQppxC/giphy.gif" width="250">
        </div>`;
    });

    noBtn.addEventListener('click', () => {
      noClickCount++;

      yesBtn.style.transform = scale(${1 + noClickCount * 0.1});

      const newMessage = document.createElement("div");
      newMessage.innerText = noMessages[Math.min(noClickCount - 1, noMessages.length - 1)];
      newMessage.style.fontSize = "14px";
      newMessage.style.color = "red";
      newMessage.style.marginTop = "5px";
      noBtn.parentNode.insertBefore(newMessage, noBtn.nextSibling);

      const angle = Math.random() * 360;
      const radius = 100 + noClickCount * 10;
      const x = Math.cos(angle) * radius;
      const y = Math.sin(angle) * radius;

      noBtn.style.position = "absolute";
      noBtn.style.left = ${Math.max(10, Math.min(window.innerWidth - 100, x + window.innerWidth / 2))}px;
      noBtn.style.top = ${Math.max(10, Math.min(window.innerHeight - 40, y + window.innerHeight / 2))}px;
    });
  </script>
</body>
</html>
