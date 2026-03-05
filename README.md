<!DOCTYPE html>
<html>
<head>
    <title>Oliver.com</title>

    <style>
        body {
            background-color: black;
            color: lime;
            font-family: monospace;
            text-align: center;
            margin-top: 50px;
        }

        #barContainer {
            width: 60%;
            background-color: grey;
            margin: 20px auto;
        }

        #bar {
            width: 0%;
            height: 30px;
            background-color: lime;
        }

        button {
            margin-top: 30px;
            font-size: 20px;
            padding: 10px 20px;
            cursor: pointer;
        }

        #warningImg {
            display: none;
            margin-top: 30px;
            max-width: 80%;
            border: 5px solid red;
        }

        .flicker {
            animation: flicker 0.1s infinite alternate;
        }

        @keyframes flicker {
            from { opacity: 1; }
            to { opacity: 0.85; }
        }
    </style>
</head>
<body>

<h1 id="title">klikk the button</h1>

<button id="startBtn">button</button>

<div id="barContainer">
    <div id="bar"></div>
</div>

<!-- Image that will appear at the end -->
<img id="warningImg" src="data:image/webp;base64,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" alt="SYSTEM WARNING">

<script>
/* -------------------
   ELEMENTS
------------------- */
const bar = document.getElementById("bar");
const title = document.getElementById("title");
const startBtn = document.getElementById("startBtn");
const warningImg = document.getElementById("warningImg");

let width = 0;

/* -------------------
   SOUND SETUP
------------------- */
let audioCtx;
function playBeep(frequency, duration) {
    if (!audioCtx) return;
    const osc = audioCtx.createOscillator();
    const gain = audioCtx.createGain();
    osc.type = "square";
    osc.frequency.value = frequency;
    osc.connect(gain);
    gain.connect(audioCtx.destination);
    osc.start();
    setTimeout(() => osc.stop(), duration);
}

/* -------------------
   FAKE SCAN FUNCTION
------------------- */
function fakeScan() {
    width++;
    bar.style.width = width + "%";
    title.innerText = "loading..." + width + "%";

    if (width >= 100) {
        clearInterval(interval);
        document.body.classList.add("flicker");
        warningImg.style.display = "block"; // show the image
        playBeep(100, 1000000);

        
    }
}

/* -------------------
   START BUTTON
------------------- */
let interval;
startBtn.addEventListener("click", () => {
    audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    startBtn.style.display = "none";
    title.innerText = "Initializing Security Scan...";
    interval = setInterval(fakeScan, 50);
});
</script>

</body>
