# valentine-site
valentine gift
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Bestie Valentine Gift 💝</title>
<style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(to bottom, #fff7ed, #dbeafe);
      font-family: "Poppins", sans-serif;
      overflow: hidden;
    }

    /* Card */
    .card {
      background: white;
      width: 390px;
      padding: 35px;
      border-radius: 30px;
      text-align: center;
      box-shadow: 0 15px 40px rgba(0,0,0,0.15);
      position: relative;
      z-index: 2;
      animation: popCard 1.2s ease;
    }

    @keyframes popCard {
      from { transform: scale(0.6); opacity: 0; }
      to   { transform: scale(1); opacity: 1; }
    }

    h1 {
      font-size: 18px;
      color: #1e293b;
      margin: 12px 0;
    }

    /* Teddy GIF */
    .teddy img {
      width: 155px;
      margin: 15px 0;
      animation: bounce 2s infinite ease-in-out;
      transition: 0.5s;
    }

    @keyframes bounce {
      0%,100% { transform: translateY(0); }
      50% { transform: translateY(-18px); }
    }

    /* Buttons Area */
    .buttons {
      margin-top: 25px;
      position: relative;
      height: 95px;
    }

    /* Aesthetic Buttons */
    button {
      padding: 14px 26px;
      border: none;
      border-radius: 25px;
      cursor: pointer;
      font-size: 15px;
      font-weight: 600;
      transition: 0.35s ease;
      position: absolute;
      box-shadow: 0 8px 15px rgba(0,0,0,0.12);
    }

    /* YES Button */
    #yesBtn {
      background: linear-gradient(135deg, #93c5fd, #60a5fa);
      color: white;
      left: 65px;
    }

    #yesBtn:hover {
      transform: scale(1.12) rotate(-2deg);
      box-shadow: 0 12px 20px rgba(0,0,0,0.18);
    }

    /* NO Button */
    #noBtn {
      background: linear-gradient(135deg, #fda4af, #fb7185);
      color: white;
      right: 65px;
    }

    #noBtn:hover {
      transform: scale(1.05) rotate(2deg);
    }

    /* Pop Click Effect */
    button:active {
      transform: scale(0.9);
    }

    /* Message */
    .message {
      display: none;
      margin-top: 0px;
      font-size: 15px;
      font-weight: 600;
      color: #0f172a;
      animation: fadeIn 1s ease;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.8); }
      to   { opacity: 1; transform: scale(1); }
    }

    /* Floating Hearts */
    .heart {
      position: absolute;
      font-size: 18px;
      opacity: 0.6;
      animation: floatUp 7s linear infinite;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(100vh) scale(0.7);
        opacity: 0;
      }
      30% { opacity: 0.8; }
      100% {
        transform: translateY(-10vh) scale(1.2);
        opacity: 0;
      }
    }
  </style>
</head>

<body>

  <div class="card">

    <!-- Title -->
    <h1>💌 for my pookie💐</h1>

    <!-- Teddy GIF (Non Anime) -->
    <div class="teddy">
      <img id="teddyImg"
        src="https://media.giphy.com/media/5GoVLqeAOo6PK/giphy.gif">
    </div>

    <!-- Question -->
    <h1 id="question">
      ini hari jadi b png kawan valentine e🤪✨
    </h1>  

    <!-- Buttons -->
    <div class="buttons">
      <button id="yesBtn" onclick="yesClicked()">Yes </button>
      <button id="noBtn" onclick="noClicked()">No </button>
    </div>

    <!-- Final Message -->
    <div class="message" id="msg">
     YAYYYY b tau lu akan bilang YES😼<br>
     HAPPY VALENTINE DAY RAHELLLL🧸🤍<br>
     jng bosan bosan dg b e 🤪 <br>
     kalo b ganggu terus jng esmosi e hehe😝<br>
     pokoknya ktg dua harus jadi kawan until the end<br>
     Wishing you happiness & success always 🌷<br>
    </div>
  </div>

  <script>
    /* NO Button Questions */
    let questions = [
      "betul sn mau jadi b png kwn valentine?????😭",
      "oh oke😤",
      "c'mon jng bikin b kas keluar kata mutiara 😆",
      "rahelll tolongg e",
      "hehe anjay mau suu 😂",
      "lu mau b boikot???",
      "oke ini terakhir su, STOP TEKAN NO",

    ];

    let index = 0;

    /* YES Click */
    function yesClicked() {

      document.getElementById("question").innerText =
        "Happy Valentine Rahel💖🐶";

      document.getElementById("msg").style.display = "block";

      /* Change GIF to Hug Bestie */
      document.getElementById("teddyImg").src =
        "https://media.giphy.com/media/3oriO0OEd9QIDdllqo/giphy.gif";

      /* Hide Buttons */
      document.getElementById("yesBtn").style.display = "none";
      document.getElementById("noBtn").style.display = "none";
    }

    /* NO Click */
    function noClicked() {
      const noBtn = document.getElementById("noBtn");

      /* Move randomly */
      let x = Math.random() * 250;
      let y = Math.random() * 70;

      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";

      /* Change Question */
      document.getElementById("question").innerText =
        questions[index];

      index++;
      if (index >= questions.length) index = 0;
    }

    /* Floating Hearts Generator */
    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.innerHTML = "🤍";

      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration =
        (4 + Math.random() * 4) + "s";

      document.body.appendChild(heart);

      setTimeout(() => heart.remove(), 7000);
    }

    setInterval(createHeart, 350);
  </script>

</body>
</html>












