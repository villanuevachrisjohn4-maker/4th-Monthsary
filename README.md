<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Favorite Nonchalant Person <3</title>

<style>
body {
    margin: 0;
    overflow: hidden;
    font-family: Arial, sans-serif;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    text-align: center;
    color: white;

    /* Super Cool Animated Background */
    background: linear-gradient(-45deg, #ff9a9e, #fad0c4, #fbc2eb, #a6c1ee);
    background-size: 400% 400%;
    animation: gradientBG 12s ease infinite;
}

@keyframes gradientBG {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}

h1 {
    font-size: 2rem;
    margin-bottom: 10px;
    z-index: 2;
}

/* Flower GIF */
.flower {
    width: 220px;
    max-width: 80vw;
    height: auto;
    animation: float 4s ease-in-out infinite;
    z-index: 2;
}

@keyframes float {
    0% { transform: translateY(0px); }
    50% { transform: translateY(-15px); }
    100% { transform: translateY(0px); }
}

/* Typing Message */
.message {
    margin-top: 20px;
    font-size: 1.2rem;
    min-height: 24px;
    border-right: 2px solid white;
    white-space: nowrap;
    overflow: hidden;
    z-index: 2;
}

/* Floating Hearts Background */
.floating-heart {
    position: absolute;
    font-size: 20px;
    opacity: 0.5;
    animation: floatUp linear infinite;
}

@keyframes floatUp {
    0% {
        transform: translateY(100vh);
        opacity: 0.7;
    }
    100% {
        transform: translateY(-10vh);
        opacity: 0;
    }
}

/* Click Burst Hearts */
.burst {
    position: absolute;
    font-size: 18px;
    pointer-events: none;
    animation: explode 800ms ease-out forwards;
}

@keyframes explode {
    0% {
        transform: scale(1) translate(0,0);
        opacity: 1;
    }
    100% {
        transform: scale(1.5) translate(var(--x), var(--y));
        opacity: 0;
    }
}

/* Music Button */
.music-btn {
    margin-top: 20px;
    padding: 8px 15px;
    background: white;
    border: none;
    border-radius: 20px;
    cursor: pointer;
    font-size: 0.9rem;
    z-index: 2;
}

.music-btn:hover {
    background: hotpink;
    color: white;
}

/* Mobile */
@media (max-width: 600px) {
    h1 { font-size: 1.5rem; }
    .flower { width: 160px; }
    .message { font-size: 1rem; }
}
</style>
</head>
<body>

<h1>For Gelie &lt;3</h1>

<img src="flower.gif" class="flower" alt="Flower">

<div class="message" id="typing"></div>

<button class="music-btn" onclick="playMusic()">Play Music 🎵</button>

<audio id="bgMusic" loop>
    <source src="music.mp3" type="audio/mpeg">
</audio>

<script>

/* Typing Effect */
const text = "Still falling for you, month after month 💕";
const typing = document.getElementById("typing");
let i = 0;

function typeEffect() {
    if (i < text.length) {
        typing.innerHTML += text.charAt(i);
        i++;
        setTimeout(typeEffect, 50);
    }
}
setTimeout(typeEffect, 800);

/* Background Floating Hearts */
function createFloatingHeart() {
    const heart = document.createElement("div");
    heart.className = "floating-heart";
    heart.innerHTML = "💖";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.animationDuration = (5 + Math.random() * 5) + "s";
    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 10000);
}
setInterval(createFloatingHeart, 800);

/* Click Burst Hearts */
document.addEventListener("click", function(e) {
    for (let i = 0; i < 8; i++) {
        const heart = document.createElement("div");
        heart.className = "burst";
        heart.innerHTML = "💗";
        heart.style.left = e.clientX + "px";
        heart.style.top = e.clientY + "px";

        const x = (Math.random() - 0.5) * 200 + "px";
        const y = (Math.random() - 0.5) * 200 + "px";
        heart.style.setProperty('--x', x);
        heart.style.setProperty('--y', y);

        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 800);
    }
});

/* Music */
function playMusic() {
    document.getElementById("bgMusic").play();
}

</script>

</body>
</html>
