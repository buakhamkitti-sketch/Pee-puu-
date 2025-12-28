# Pee-puu-
<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kuromi x My Melody 💜🎀</title>

<style>
body {
    margin: 0;
    font-family: 'Comic Sans MS', sans-serif;
    background: linear-gradient(180deg, #2b0033, #ffb3d9);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.game {
    width: 92%;
    max-width: 380px;
    background: #fff0f7;
    border-radius: 30px;
    padding: 20px;
    text-align: center;
    box-shadow: 0 12px 30px rgba(0,0,0,0.3);
}

h1 {
    color: #6a0dad;
    font-size: 22px;
}

.name {
    color: #ff1493;
    font-size: 20px;
    margin-bottom: 5px;
}

.chars {
    font-size: 70px;
    margin: 10px 0;
}

#tap {
    font-size: 75px;
    cursor: pointer;
    transition: transform 0.15s;
}

#tap:active {
    transform: scale(1.3);
}

#score {
    margin-top: 10px;
    font-size: 22px;
    color: #b30086;
}

#msg {
    display: none;
    margin-top: 20px;
    font-size: 20px;
    color: #800040;
}

button {
    margin-top: 15px;
    padding: 10px 20px;
    border-radius: 20px;
    border: none;
    background: #6a0dad;
    color: white;
    font-size: 16px;
}
</style>
</head>

<body>
<div class="game">
    <div class="name">💖 พี่ปู้คนสวย 💖</div>
    <h1>Kuromi x My Melody</h1>

    <div class="chars">😈🎀🐰</div>

    <p>กดหัวใจให้ครบ 8 ดวงนะ</p>

    <div id="tap">💜</div>
    <div id="score">0 / 8</div>

    <div id="msg">
        🎀🐰 My Melody บอกว่า…<br>
        <b>พี่ปู้คนสวย น่ารักที่สุดเลย 💕</b><br><br>
        😈💜 ถึงจะดื้อ แต่เค้ารักพี่ปู้คนสวยคนเดียว<br>
        อยู่ด้วยกันนาน ๆ นะ 🥺💖
        <br>
        <button onclick="location.reload()">เล่นอีกครั้ง</button>
    </div>
</div>

<script>
let score = 0;
const tap = document.getElementById("tap");
const scoreText = document.getElementById("score");
const msg = document.getElementById("msg");

// เสียงปิ๊งน่ารัก ๆ
const audioCtx = new (window.AudioContext || window.webkitAudioContext)();

function playSound(){
    const osc = audioCtx.createOscillator();
    const gain = audioCtx.createGain();
    osc.type = "triangle";
    osc.frequency.value = 880;
    gain.gain.value = 0.15;

    osc.connect(gain);
    gain.connect(audioCtx.destination);

    osc.start();
    osc.stop(audioCtx.currentTime + 0.15);
}

tap.onclick = () => {
    playSound();
    score++;
    scoreText.textContent = score + " / 8";

    if(score >= 8){
        tap.style.display = "none";
        msg.style.display = "block";
    }
}
</script>
</body>
</html>
