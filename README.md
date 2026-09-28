<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gửi Kim Ngân 💗</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, sans-serif;
      min-height: 100vh;
      overflow-x: hidden;
      background: linear-gradient(135deg, #ff758c, #ff7eb3, #ffb6c1);
      color: white;
    }

    .container {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 25px;
    }

    .card {
      width: 100%;
      max-width: 500px;
      padding: 30px 22px;
      text-align: center;
      border-radius: 30px;
      background: rgba(255,255,255,0.15);
      backdrop-filter: blur(15px);
      box-shadow: 0 15px 40px rgba(0,0,0,0.2);
      border: 1px solid rgba(255,255,255,0.3);
    }

    h1 {
      font-size: 38px;
      margin-bottom: 10px;
    }

    .subtitle {
      font-size: 17px;
      margin-bottom: 25px;
      opacity: .9;
    }

    .photo {
      width: 220px;
      height: 280px;
      object-fit: cover;
      border-radius: 25px;
      border: 4px solid white;
      box-shadow: 0 10px 30px rgba(0,0,0,.25);
      margin-bottom: 25px;
    }

    .message {
      min-height: 130px;
      font-size: 18px;
      line-height: 1.7;
      margin: 20px 0;
    }

    button {
      border: none;
      padding: 14px 25px;
      border-radius: 30px;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      background: white;
      color: #ff4f81;
      box-shadow: 0 8px 20px rgba(0,0,0,.2);
      transition: .2s;
    }

    button:active {
      transform: scale(.95);
    }

    .hidden {
      display: none;
    }

    #final {
      margin-top: 20px;
      font-size: 22px;
      font-weight: bold;
      animation: appear 1s ease;
    }

    @keyframes appear {
      from {
        opacity: 0;
        transform: scale(.7);
      }
      to {
        opacity: 1;
        transform: scale(1);
      }
    }

    .heart {
      position: fixed;
      bottom: -30px;
      font-size: 20px;
      animation: fly 5s linear forwards;
      pointer-events: none;
    }

    @keyframes fly {
      0% {
        transform: translateY(0) rotate(0);
        opacity: 1;
      }

      100% {
        transform: translateY(-110vh) rotate(360deg);
        opacity: 0;
      }
    }

    .music {
      margin-top: 18px;
      font-size: 13px;
      opacity: .8;
    }

    audio {
      width: 100%;
      margin-top: 10px;
    }
  </style>
</head>

<body>

<div class="container">

  <div class="card">

    <h1>Gửi Kim Ngân 💗</h1>

    <p class="subtitle">
      Có một điều mình muốn nói với Ngân...
    </p>

    <!-- ĐỔI ẢNH Ở ĐÂY -->
    <img
      src="anh1.jpg"
      class="photo"
      alt="Kim Ngân">

    <div class="message" id="message">
      Nhấn vào nút bên dưới nhé...
    </div>

    <button onclick="startLove()">
      💌 Mở lời nhắn
    </button>

    <div id="final" class="hidden">
      Kim Ngân à...<br><br>
      Mình không biết phải nói sao cho thật hay,
      nhưng mình thật sự rất quý Ngân. ❤️
      <br><br>
      Mình muốn được ở bên Ngân,
      cùng nói chuyện, cùng vui,
      cùng chia sẻ những chuyện nhỏ nhặt mỗi ngày.
      <br><br>
      <b>Ngân cho mình một cơ hội được không? 💗</b>
    </div>

    <div class="music">
      🎵 Một bài hát dành cho Ngân
      <audio controls>
        <source src="nhac.mp3" type="audio/mpeg">
      </audio>
    </div>

  </div>

</div>

<script>

const messages = [
  "Có một người mà dạo này mình nghĩ đến khá nhiều...",
  "Mỗi lần nói chuyện với người đó mình đều cảm thấy vui hơn một chút.",
  "Mình cũng chẳng biết từ lúc nào...",
  "Nhưng người đó đã trở nên đặc biệt với mình.",
  "Và người đó chính là Ngân. 💗"
];

let index = 0;

function startLove() {

  const message = document.getElementById("message");
  const final = document.getElementById("final");

  message.innerHTML = "";

  function showNext() {

    if (index < messages.length) {

      message.innerHTML = messages[index];

      index++;

      createHearts();

      setTimeout(showNext, 2200);

    } else {

      final.classList.remove("hidden");

      for(let i = 0; i < 20; i++) {
        setTimeout(createHearts, i * 100);
      }

    }
  }

  showNext();
}

function createHearts() {

  const heart = document.createElement("div");

  heart.className = "heart";

  const hearts = ["❤️","💗","💕","💖","💘"];

  heart.innerHTML =
    hearts[Math.floor(Math.random() * hearts.length)];

  heart.style.left =
    Math.random() * 100 + "vw";

  heart.style.fontSize =
    (15 + Math.random() * 25) + "px";

  heart.style.animationDuration =
    (3 + Math.random() * 4) + "s";

  document.body.appendChild(heart);

  setTimeout(() => {
    heart.remove();
  }, 7000);
}

</script>

</body>
</html>
