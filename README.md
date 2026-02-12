<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Galentine Sweetheart 💗</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
:root {
  --bg: #ffe6f0;
  --card: #ffffff;
  --primary: #ff5c8a;
  --secondary: #ff99c8;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: linear-gradient(135deg, var(--bg), #fff);
  overflow-x: hidden;
}

section {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 20px;
}

.card {
  background: var(--card);
  padding: 25px;
  border-radius: 16px;
  max-width: 360px;
  box-shadow: 0 8px 20px rgba(0,0,0,0.15);
}

h1 { color: var(--primary); }

button {
  background: var(--primary);
  color: white;
  border: none;
  padding: 12px 20px;
  border-radius: 20px;
  font-size: 16px;
  margin: 8px;
  cursor: pointer;
}

button:hover {
  background: var(--secondary);
}

#noBtn {
  position: relative;
}

.confetti {
  position: fixed;
  top: -10px;
  width: 10px;
  height: 10px;
  animation: fall 3s linear infinite;
}

@keyframes fall {
  to { transform: translateY(110vh) rotate(360deg); }
}
</style>
</head>
<body>

<audio id="bgMusic" src="song.mp3" loop></audio>

<section>
  <div class="card">
    <h1>Happy Galentine, Sweetheart 💗</h1>
    <p>
      You’re literally my comfort person 🥺💞  
      Everything feels better when you’re around.
    </p>
    <button onclick="start()">Start Here</button>
  </div>
</section>

<section id="ask" style="display:none;">
  <div class="card">
    <h1>Sweetheart, will you be my Galentine? 💕</h1>
    <button onclick="yes()">Yes, obviously! 😌💗</button>
    <button id="noBtn" onmouseover="moveNo()">NO! 😒</button>
  </div>
</section>

<section id="yay" style="display:none;">
  <div class="card">
    <h1>YAYYYY 🥳💞</h1>
    <p>
      Best friends forever ♾️  
      From our cute lil fights over Mansi to our silly jealousy & possessiveness 😭💗
    </p>
    <p>
      No matter what, it’s always you and me 🫶💞
    </p>
  </div>
</section>

<script>
function start() {
  document.getElementById("bgMusic").play().catch(()=>{});
  document.getElementById("ask").style.display = "flex";
  window.scrollTo(0, document.body.scrollHeight);
}

function moveNo() {
  const b = document.getElementById("noBtn");
  b.style.left = Math.random() * 240 - 120 + "px";
  b.style.top = Math.random() * 240 - 120 + "px";
}

function yes() {
  document.getElementById("yay").style.display = "flex";
  for (let i = 0; i < 40; i++) {
    const c = document.createElement("div");
    c.className = "confetti";
    c.style.left = Math.random() * 100 + "vw";
    c.style.background = ["#ff5c8a","#ff99c8","#ffc2d1"][Math.floor(Math.random()*3)];
    c.style.animationDelay = Math.random() * 2 + "s";
    document.body.appendChild(c);
  }
  window.scrollTo(0, document.body.scrollHeight);
}
</script>

</body>
</html>