<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>❤元気メッセージ❤</title>
<style>
  body {
    background-color: #ffeef5;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    font-family: 'Meiryo', sans-serif;
  }
  button {
    background-color: #ff8fcf;
    border: none;
    padding: 12px 24px;
    border-radius: 12px;
    font-size: 18px;
    color: white;
    cursor: pointer;
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    transition: all 0.3s;
  }
  button:hover {
    background-color: #ff66b2;
    transform: scale(1.05);
  }
  .popup {
    position: fixed;
    padding: 10px 20px;
    border-radius: 15px;
    font-weight: bold;
    color: #333;
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    z-index: 9999;
    animation: fadeInOut 6s forwards;
  }
  @keyframes fadeInOut {
    0% {opacity: 0;}
    10% {opacity: 1;}
    90% {opacity: 1;}
    100% {opacity: 0;}
  }
</style>
</head>
<body>

<h1>❤元気メッセージ❤</h1>
<button onclick="startPopups()">開始する</button>

<script>
const messages = [
  "笑顔でいこう！😊",
  "今日も一日がんばろう！💪",
  "君ならできる！🌟",
  "焦らず、少しずつ前へ✨",
  "きっと大丈夫！🌈",
  "休むことも大事だよ☕",
  "夢はきっと叶うよ💭",
  "自分を信じてね💖",
  "無理しないでね🍀",
  "毎日少しずつ成長しよう🌱"
];

const colors = [
  'lightpink', 'skyblue', 'lightgreen', 'lavender', 'lightyellow', 'plum',
  'coral', 'bisque', 'aquamarine', 'mistyrose', 'honeydew', 'peachpuff',
  'paleturquoise', 'lavenderblush', 'oldlace', 'lemonchiffon', 'lightcyan'
];

function randomChoice(arr) {
  return arr[Math.floor(Math.random() * arr.length)];
}

function showPopup() {
  const popup = document.createElement('div');
  popup.className = 'popup';
  // 在消息前加上 ftx: 前缀
  popup.textContent = "ftx: " + randomChoice(messages);
  popup.style.backgroundColor = randomChoice(colors);
  
  const x = Math.random() * (window.innerWidth - 200);
  const y = Math.random() * (window.innerHeight - 100);
  
  popup.style.left = `${x}px`;
  popup.style.top = `${y}px`;
  
  document.body.appendChild(popup);
  
  setTimeout(() => popup.remove(), 6000);
}

function startPopups() {
  let count = 0;
  const total = 100; // 弹出数量（可以改成 350）
  const interval = setInterval(() => {
    showPopup();
    count++;
    if (count >= total) clearInterval(interval);
  }, 150);
}
</script>

</body>
</html>
