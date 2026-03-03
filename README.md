<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Kayle <3</title>

<style>
body {
    margin: 0;
    background: #ffffff;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    font-family: 'Arial', sans-serif;
    overflow: hidden;
    text-align: center;
}

h1 {
    margin-bottom: 10px;
    font-size: 2rem;
}

.message {
    font-size: 1.2rem;
    margin-top: 20px;
    opacity: 0;
    animation: fadeIn 3s ease forwards;
    animation-delay: 2s;
}

@keyframes fadeIn {
    to { opacity: 1; }
}

/* SVG Flower */
.flower {
    width: 200px;
    animation: sway 4s ease-in-out infinite;
}

@keyframes sway {
    0% { transform: rotate(-3deg); }
    50% { transform: rotate(3deg); }
    100% { transform: rotate(-3deg); }
}

/* Floating Hearts */
.heart {
    position: absolute;
    color: pink;
    font-size: 20px;
    animation: floatUp 6s linear infinite;
    opacity: 0.8;
}

@keyframes floatUp {
    0% {
        transform: translateY(100vh);
        opacity: 1;
    }
    100% {
        transform: translateY(-10vh);
        opacity: 0;
    }
}

/* Mobile adjustments */
@media (max-width: 600px) {
    .flower {
        width: 150px;
    }
    h1 {
        font-size: 1.5rem;
    }
}
</style>
</head>
<body>

<h1>For Kayle &lt;3</h1>

<!-- SVG Sunflower -->
<svg class="flower" viewBox="0 0 200 300">
    <!-- Stem -->
    <rect x="95" y="120" width="10" height="150" fill="green" />
    <!-- Leaves -->
    <ellipse cx="70" cy="180" rx="30" ry="15" fill="green" transform="rotate(-30 70 180)"/>
    <ellipse cx="130" cy="210" rx="30" ry="15" fill="green" transform="rotate(30 130 210)"/>
    <!-- Petals -->
    <g fill="gold">
        <circle cx="100" cy="100" r="60"/>
    </g>
    <!-- Center -->
    <circle cx="100" cy="100" r="40" fill="brown"/>
</svg>

<div class="message">
    Everything I ever wanted in a flower is here 🌼
</div>

<!-- Background Music -->
<audio autoplay loop>
    <source src="music.mp3" type="audio/mpeg">
</audio>

<script>
/* Floating Hearts Generator */
function createHeart() {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "💗";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.animationDuration = (4 + Math.random() * 4) + "s";
    document.body.appendChild(heart);

    setTimeout(() => {
        heart.remove();
    }, 7000);
}

setInterval(createHeart, 800);
</script>

</body>
</html>
