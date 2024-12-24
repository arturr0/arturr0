<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>

.typing-container {
    display: inline-block;
    font-family: monospace; /* Classic typing effect */
    font-size: 24px;
    white-space: nowrap; /* Prevent text from wrapping */
    overflow: hidden; /* Hide overflowing text */
}

.cursor {
    display: inline-block;
    animation: blinkCursor 0.75s infinite; /* Blink every 0.75 seconds */
    font-size: inherit; /* Match the font size */
    color: black; /* Color of the cursor */
}

@keyframes blinkCursor {
    0%, 100% {
        opacity: 1;
    }
    50% {
        opacity: 0;
    }
}

    </style>
    <title>Document</title>
</head>
<body>
    <div class="typing-container">
        <span id="text"></span>
        <span class="cursor">_</span>
    </div>
    <script>
//         const text = "Hello, this is a typing animation!";
// const textElement = document.getElementById("text");
// let index = 0;

// function type() {
//     if (index < text.length) {
//         textElement.textContent += text.charAt(index);
//         index++;
//         setTimeout(type, 150); // Adjust typing speed here (in milliseconds)
//     }
// }

// type();
const text = "Hello, this is a typing animation!";
const textElement = document.getElementById("text");
let index = 0;
let isTyping = true; // Flag to track if we are typing or erasing

function type() {
    if (index < text.length) {
        textElement.textContent += text.charAt(index);
        index++;
        setTimeout(type, 150); // Typing speed
    } else {
        // Start erasing after a delay
        setTimeout(erase, 1000); // Wait 1 second before starting to erase
    }
}

function erase() {
    if (index > 0) {
        textElement.textContent = text.substring(0, index - 1);
        index--;
        setTimeout(erase, 100); // Erasing speed
    } else {
        // After erasing, start typing again
        setTimeout(type, 500); // Wait before typing again
    }
}

type();


    </script>    
    
