<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Motu ❤️</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 100%);
            font-family: 'Poppins', sans-serif;
            text-align: center;
            overflow: hidden;
        }

  #card {
            background: rgba(255, 255, 255, 0.9);
            padding: 30px;
            border-radius: 25px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
            max-width: 450px;
            width: 85%;
            z-index: 10;
            border: 2px solid #ff4d6d;
        }

  h1 { color: #ff4d6d; font-size: 24px; margin-bottom: 10px; }
        p { color: #555; font-size: 18px; }
        .sub-text { font-size: 14px; color: #ff758c; font-style: italic; }

  .btn-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
            height: 50px;
        }

button {
            padding: 10px 25px;
            font-size: 1.1rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-weight: bold;
            transition: 0.3s;
        }

.yes-btn { background-color: #ff4d6d; color: white; box-shadow: 0 4px 15px rgba(255, 77, 109, 0.4); }
        .no-btn { background-color: #eee; color: #333; position: absolute; }

  .sticker { font-size: 60px; display: block; margin-bottom: 15px; }
       .hidden { display: none; }

   /* Floating Hearts Animation */
        .heart {
            position: absolute;
            color: #ff4d6d;
            font-size: 20px;
            animation: float 5s linear infinite;
            top: 100vh;
        }

   @keyframes float {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-100vh) rotate(360deg); opacity: 0; }
        }
    </style>
</head>
<body>

<div id="card">
        <div id="step1">
            <span class="sticker">🌹</span>
            <h1>Meri Pyari Motu...</h1>
            <p>Will you be my Valentine?</p>
            <div class="btn-container">
                <button class="yes-btn" onclick="showStep(2)">Yes</button>
                <button id="no1" class="no-btn" onmouseover="moveButton('no1')">No</button>
            </div>
        </div>

 <div id="step2" class="hidden">
            <span class="sticker">💍</span>
            <h1>Wait, ek aur baat...</h1>
            <p>Will you be my Begum G?</p>
            <div class="btn-container">
                <button class="yes-btn" onclick="showStep(3)">Yes</button>
                <button id="no2" class="no-btn" onmouseover="moveButton('no2')">No</button>
            </div>
        </div>
      <div id="step3" class="hidden">
            <span class="sticker">🍼</span>
            <h1>Suno toh!</h1>
            <p>Will you be my bacho ki ama?</p>
            <p class="sub-text">Ab tu practice b ho gai ha 😂</p>
            <div class="btn-container">
                <button class="yes-btn" onclick="showStep(4)">Yes</button>
                <button id="no3" class="no-btn" onmouseover="moveButton('no3')">No</button>
            </div>
        </div>
    <div id="step4" class="hidden">
            <span class="sticker">🥺</span>
            <h1 style="color: #d63384;">I Love You! ❤️</h1>
            <hr style="border: 0.5px solid #ffc2d1; margin: 20px 0;">
            <span class="sticker">🤣</span>
            <p>Now you are queen of my heart...</p>
            <p style="font-weight: bold; color: #ff4d6d;">Meri life mein ek "Motu" pehle se hai! 💅</p>
        </div>
    </div>
    <script>
        // Move "No" Button function
        function moveButton(id) {
            const btn = document.getElementById(id);
            const x = Math.random() * (window.innerWidth - btn.clientWidth - 50);
            const y = Math.random() * (window.innerHeight - btn.clientHeight - 50);
            btn.style.position = 'fixed';
            btn.style.left = x + 'px';
            btn.style.top = y + 'px';
        }

   // Change pages
        function showStep(stepNum) {
            document.getElementById('step1').classList.add('hidden');
            document.getElementById('step2').classList.add('hidden');
            document.getElementById('step3').classList.add('hidden');
            document.getElementById('step' + stepNum).classList.remove('hidden');
                 // Re-center "No" buttons for next page if needed
            if(stepNum < 4) {
                const nextNo = document.getElementById('no' + stepNum);
                if(nextNo) {
                    nextNo.style.position = 'absolute';
                    nextNo.style.left = '55%';
                    nextNo.style.top = 'auto';
                }
            }
        }

  // Background Hearts
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 3 + 2 + 's';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }
        setInterval(createHeart, 400);
    </script>
</body>
</html>
