<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Pour Maïssa</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            color: white;
            text-align: center;
        }

        h1 {
            margin-top: 120px;
            font-size: 2.5em;
        }

        p {
            font-size: 1.2em;
        }

        button {
            padding: 15px 25px;
            font-size: 1.2em;
            margin: 20px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
        }

        #yesBtn {
            background-color: #ff4d6d;
            color: white;
        }

        #noBtn {
            background-color: white;
            color: #ff4d6d;
            position: absolute;
        }

        .message {
            margin-top: 30px;
            font-size: 1.5em;
        }

        .heart {
            position: absolute;
            top: -50px;
            font-size: 20px;
            color: rgba(255,255,255,0.7);
            animation: fall linear infinite;
        }

        @keyframes fall {
            to {
                transform: translateY(110vh);
            }
        }
    </style>
</head>
<body>

    <h1>Maïssa, est-ce que tu veux sortir avec moi au parc tout à l’heure ?</h1>

    <p>On pourrait se balader tranquillement, discuter et passer un bon moment ensemble.</p>
    <p>Promis je serai vraiment agréable.</p>

    <button id="yesBtn" onclick="sayYes()">Oui</button>
    <button id="noBtn" onmouseover="moveButton()">Non</button>

    <div class="message" id="message"></div>

    <script>
        function sayYes() {
            document.getElementById("message").innerHTML =
                "Je savais que tu dirais oui. J’ai hâte de passer ce moment avec toi.";
        }

        function moveButton() {
            const btn = document.getElementById("noBtn");
            const x = Math.random() * (window.innerWidth - 100);
            const y = Math.random() * (window.innerHeight - 50);

            btn.style.left = x + "px";
            btn.style.top = y + "px";
        }

        // Génération des cœurs animés
        function createHeart() {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            heart.innerHTML = "❤";
            heart.style.left = Math.random() * 100 + "vw";
            heart.style.animationDuration = (Math.random() * 3 + 2) + "s";
            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 5000);
        }

        setInterval(createHeart, 300);
    </script>

</body>
</html>
