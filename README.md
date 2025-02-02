<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #ffe6f2;
            font-family: sans-serif;
        }

        .container {
            text-align: center;
        }

        h1 {
            color: #ff69b4;
        }

        .buttons {
            margin-top: 20px;
        }

        button {
            padding: 10px 20px;
            margin: 0 10px;
            border: none;
            border-radius: 5px;
            background-color: #ff69b4;
            color: white;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        #yesButton {
            font-size: 16px;
        }

        #noButton {
            font-size: 16px;
        }

        .message {
            margin-top: 20px;
            color: #ff69b4;
        }

        .characters {
            margin-top: 20px;
        }

        .characters img {
            width: 100px;
            height: 100px;
            margin: 0 10px;
        }

        .yes-message {
            font-size: 2em;
            color: #ff69b4;
            animation: pulse 1s infinite;
        }

        @keyframes pulse {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.1);
            }
            100% {
                transform: scale(1);
            }
        }
    </style>
</head>

<body>
    <div class="container">
        <h1>Will You Be My Valentine?</h1>
        <div class="buttons">
            <button id="yesButton">Yes!</button>
            <button id="noButton">No</button>
        </div>
        <div class="message" id="message"></div>
        <div class="characters" id="characters"></div>
    </div>

    <script>
        const yesButton = document.getElementById("yesButton");
        const noButton = document.getElementById("noButton");
        const message = document.getElementById("message");
        const characters = document.getElementById("characters");
        let noButtonScale = 1;
        let yesButtonScale = 1;
        let noClicks = 0;

        yesButton.addEventListener("click", () => {
            message.textContent = "Yiee HAHAHA are for real?";
            message.classList.add("yes-message");
            characters.innerHTML = `
                <img src="https://images.app.goo.gl/G43BGY5pouSaP9er6.gif" alt="">
                <img src="https://images.app.goo.gl/so6bPUgnDTeYSnHY7.gif" alt="">
            `;
        });

        noButton.addEventListener("click", () => {
            noClicks++;
            if (noClicks >= 3) {
                noButton.style.display = "none";
                message.textContent = "Please Mwa Mwa! 😉";
            } else {
                message.textContent = "Aww, that's okay. Maybe next time. 🤔👉👈";
                message.classList.remove("yes-message");
                characters.innerHTML = "";
                noButtonScale -= 0.1;
                yesButtonScale += 0.1;
                noButton.style.transform = `scale(${noButtonScale})`;
                yesButton.style.transform = `scale(${yesButtonScale})`;
                if (noButtonScale < 0.5) {
                    noButton.disabled = true;
                    message.textContent = "Okay, okay, I understand! 😅 You can always change your mind😉";
                }
            }
        });
    </script>
    <address>
        <p>
            <a href="https://www.facebook.com/zyderjames.sabado.90?mibextid=ZbWKwL">
                <p style="font-family:courier">Created By Zyder.</p>
            </a>
        </p>
    </address>
</body>

</html>
