<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Valentine</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: pink;
            font-family: Arial, sans-serif;
            text-align: center;
        }
        .container {
            text-align: center;
        }
        h1 {
            color: #d00000;
            font-size: 24px;
            font-weight: bold;
        }
        .buttons {
            margin-top: 10px;
        }
        .button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 5px;
            cursor: pointer;
            border: none;
            border-radius: 5px;
            transition: transform 0.2s ease-in-out;
        }
        .yes-button {
            background-color: #4caf50;
            color: white;
        }
        .no-button {
            background-color: #f44336;
            color: white;
        }
        .button:hover {
            transform: scale(1.1);
        }
        .sticker img {
            margin-top: 10px;
            width: 150px;
        }
        .final-message, .final-sticker {
            margin-top: 20px;
            font-size: 18px;
            color: #333;
            display: none;
        }
        .final-sticker img {
            width: 250px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>can you be my date?</h1>
        <div class="buttons">
            <button class="button yes-button" id="yesButton">Yes</button>
            <button class="button no-button" id="noButton">No</button>
        </div>
        
        <!-- First Sticker (Initially Visible) -->
        <div class="sticker" id="firstSticker">
            <img src="https://media.giphy.com/media/VM1fcpu2bKs1e2Kdbj/giphy.gif" alt="Cute animated sticker">
        </div>

        <!-- Final Message and Second Sticker (Hidden Initially) -->
        <div class="final-message" id="finalMessage">would you say yes!</div>
        <div class="final-sticker" id="finalSticker">
            <img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExZ2JwOHdrbTRwcjVjeW8zanl5NDljcWtvMW5xZWQ0azVybjc3Y2pvZyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/3o752k5H19mo1pnpkc/giphy.gif" alt="Excited animated sticker">
        </div>
    </div>

    <script>
        const yesButton = document.getElementById('yesButton');
        const noButton = document.getElementById('noButton');
        const firstSticker = document.getElementById('firstSticker');
        const finalMessageDiv = document.getElementById('finalMessage');
        const finalStickerDiv = document.getElementById('finalSticker');
        let clickCount = 0;

        const messages = [
            "Are you sure?",
            "Really Sure??",
            "Are you positive?",
            "Pookie Please",
            "Just think about it!!",
            "If you say no, I will be really sad...",
            "I will be very sad",
            "I will be very very very sad..."
        ];

        noButton.addEventListener('click', () => {
            if (clickCount < messages.length) {
                noButton.textContent = messages[clickCount];
                clickCount++;
            } else {
                yesButton.style.width = '100vw';
                yesButton.style.height = '100vh';
                yesButton.style.fontSize = '50px';
                yesButton.textContent = "YES!";
                noButton.style.display = 'none';
            }
            let currentSize = parseInt(window.getComputedStyle(yesButton).fontSize);
            yesButton.style.fontSize = (currentSize + 5) + 'px';
        });

        yesButton.addEventListener('click', () => {
            finalMessageDiv.style.display = 'block';
            finalStickerDiv.style.display = 'block';
            firstSticker.style.display = 'none'; // Hide the first sticker
            yesButton.style.display = 'none';
            noButton.style.display = 'none';
        });
    </script>
</body>
</html>
``` ▋
