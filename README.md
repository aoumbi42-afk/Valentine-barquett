<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Pour toi 💖</title>
<style>
    body {
        margin: 0;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background: linear-gradient(135deg, #ff9a9e, #fad0c4);
        font-family: Arial, sans-serif;
        overflow: hidden;
        text-align: center;
    }

    .card {
        background: white;
        padding: 40px;
        border-radius: 20px;
        box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        max-width: 400px;
        position: relative;
        z-index: 2;
    }

    h1 {
        margin-bottom: 25px;
    }

    button {
        padding: 12px 25px;
        font-size: 16px;
        border: none;
        border-radius: 30px;
        margin: 10px;
        cursor: pointer;
        transition: 0.2s;
    }

    #yes {
        background: #ff4d6d;
        color: white;
    }

    #no {
        background: #ddd;
        position: relative;
    }

    .heart {
        position: fixed;
        top: -10px;
        font-size: 20px;
        animation: fall linear forwards;
    }

    @keyframes fall {
        to {
            transform: translateY(110vh);
            opacity: 0;
        }
    }
</style>
</head>
<body>

<div class="card">
    <h1>💖 Veux-tu être ma Valentine ? 💖</h1>
    <button id="yes" onclick="sayYes()">Oui 🥰</button>
    <button id="no" onmouseover="moveNo()">Non 😈</button>
</div>

<script>
function sayYes() {
    document.body.innerHTML = "<h1 style='color:white;font-size:40px;'>YAYYY 🥹💘<br>Tu viens de me rendre le plus heureux du monde</h1>";
    startHearts();
}

function moveNo() {
    const btn = document.getElementById("no");
    btn.style.position = "absolute";
    btn.style.left = Math.random() * 80 + "%";
    btn.style.top = Math.random() * 80 + "%";
}

function startHearts() {
    setInterval(() => {
        const heart = document.createElement("div");
        heart.className = "heart";
        heart.innerHTML = "💖";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDuration = (Math.random() * 2 + 3) + "s";
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 5000);
    }, 300);
}
</script>

</body>
</html>
