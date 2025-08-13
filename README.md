<!DOCTYPE html>
<html lang="en" >
<head>
  <meta charset="UTF-8">
  <title>ini aman kok bukan phising </title>
  

</head>
<body>
<!-- partial:index.partial.html -->
lang="en">
<head>
<meta charset="UTF-8">
<title>bukan yg aneh aneh pokoknya</title>
<style>
    body {
        background: black;
        color: #89E6ED;
        font-family: monospace;
        padding: 20px;
        font-size: 16px;
    }
    .cursor {
        display: inline-block;
        width: 10px;
        height: 20px;
        background: #89E6ED;
        animation: blink 0.7s infinite;
        vertical-align: bottom;
    }
    @keyframes blink {
        0%, 100% { opacity: 1; }
        50% { opacity: 0; }
    }
</style>
</head>
<body>

<pre id="output"></pre>

<script>
// Pesan rahasia persis seperti contoh pertama, ditambah ASCII art bunga
const message = `=== PESAN RAHASIA ===
Halo, jika kamu membaca ini berati al udh kena karmanya 
       maafin Al ya

⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣀⠀⠀⠀⣀⣀⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⢀⣀⣀⢠⠿⠷⣭⣶⣯⣥⣶⣾⣿⠀⠀⠀⠀⢠⠖⣒⡒⢢⣄⡴⠒⢢⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⢸⠷⣾⣿⡀⢠⡿⠑⠀⠀⢸⣿⡿⡄⠀⠀⠀⢸⢼⣍⠙⠛⠙⢷⡀⠀⣷⠒⠈⡆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⢸⣼⡟⣭⣻⢿⣧⡀⠀⣰⡿⠛⣫⣽⠀⠀⢠⠃⠈⢾⣄⠀⠀⢸⣷⡶⠓⢷⣄⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠈⣿⡏⠀⠈⠀⠙⣿⣴⡿⠁⠀⠁⢸⠂⠀⢸⠀⠀⠀⢫⣆⣰⡟⠁⠀⠀⢈⣿⠃⠀⠀⡀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠸⣷⠀⠀⠀⠀⠘⣿⡇⠀⠀⢀⡟⠀⠀⠘⡆⠀⠀⠀⣿⡏⠀⠀⠀⠀⣸⡏⠀⠀⣾⣿⣿⣿⣶⣾⡝⡆⣀⡀
⠀⠀⠀⠀⠀⢀⡠⣤⠤⡀⠈⢧⡀⠀⠀⠀⣻⡇⠀⣠⠞⠀⠀⠀⠀⠙⢄⡀⠀⣿⠁⠀⠀⠀⣰⠋⠀⠀⡰⣿⢿⣏⠀⠹⣷⣿⣿⣿⣿
⠀⠀⡞⠉⢱⡾⠾⠛⣷⠷⡀⠀⠙⠦⠤⢤⣿⣿⠟⠀⠀⠀⠀⠀⢀⣴⣀⠭⢶⣿⣤⣄⠤⠞⠁⠀⠀⠀⣿⣿⠎⢿⣦⣾⠟⠏⠾⣿⡇
⡖⢒⣇⡀⣿⠀⠀⢠⡟⠀⠘⡆⠀⠀⠀⠀⠀⣿⠀⠀⠀⠀⠀⣠⣿⣿⡇⠀⢰⡏⠀⠈⠑⠢⣄⡀⠀⠀⢻⡹⠀⢸⡿⠁⠀⠂⣰⡟⠀
⠱⣼⠋⠉⠛⠷⣤⣼⠁⠀⠀⢱⠀⠀⠀⠀⠀⢹⡇⠀⠀⡠⢺⣿⣿⣿⡇⠀⣼⠇⠀⠀⠀⠀⠀⣭⠲⢄⡀⠙⢦⣼⣧⠄⢀⡴⠋⠀⠀
⠀⠻⣆⠀⠀⠀⠈⢻⡄⠀⢀⠆⠀⠀⠀⣰⡄⠘⣷⢀⡜⠁⣾⣿⣿⣿⡇⢀⡿⠀⠀⠀⣴⣧⢸⣿⣧⠀⠉⠲⢄⣿⠋⠉⠉⠀⠀⠀⠀
⠀⠀⠙⢦⡀⠀⠀⠀⣧⣴⠋⠀⠀⠀⢠⣿⣿⡄⢿⡎⠀⢸⣿⣿⣿⣿⡇⢸⡇⠀⢀⣾⣿⣿⣾⣿⣿⡇⠀⠀⢸⠏⠑⠢⣀⣤⡶⠀⠀
⠀⠀⠀⠀⠈⠁⠒⠈⠙⣯⠀⠀⠀⠀⣼⣿⣿⣿⣼⡇⠀⣿⣿⣿⣿⣿⠃⣾⠃⢀⣿⣿⣿⡇⣿⣿⣿⣧⠀⢀⡿⠀⢀⣴⣿⣿⡇⠀⠀
⠀⠀⠀⢀⣀⠀⠀⠀⠀⠘⣷⠀⠀⠀⣿⣿⣿⣿⣟⡇⢠⣿⣿⣿⣿⡟⢀⣿⢀⣾⣿⣿⣿⠇⢿⣿⣿⣿⠀⣸⠇⢠⣾⣿⣿⠏⢣⠀⠀
⠀⠀⠀⠈⢿⣿⣦⣄⠀⠀⠘⣧⠀⢀⣿⣿⣿⣿⣿⣿⢸⣿⣿⣿⡿⠁⢸⡏⣸⣿⣿⣿⡟⠀⠸⣿⣿⣿⢀⡿⢠⣿⣿⣿⠏⠀⠀⡇⠀
⠀⠀⠀⠀⠈⢿⣿⣿⣷⣄⠀⣸⣷⠉⣿⣿⣿⣿⣿⢹⣸⣿⣿⡿⠁⠀⢸⣇⣿⣿⣿⡟⠀⠀⠀⠹⣿⣿⣼⢧⣿⣿⠟⠁⢀⢔⡫⠆⠀
⠀⠀⠀⠀⠀⠈⠻⣿⣿⣿⣿⣄⠹⡆⢹⣿⣿⣿⡟⢸⣿⡿⠋⡀⠀⠀⣿⢹⣿⣿⠏⢀⣴⣿⠀⠀⠙⢿⣿⠛⠋⢁⡠⣺⠔⠉⠀⠀⠀
⠀⠀⠀⠀⠀⠀⣠⠟⢿⣿⣿⣿⣧⣹⡜⣿⣿⣿⠇⢸⣧⠀⢰⣿⡀⠀⣿⠸⠟⠁⠀⣾⣿⡟⠀⠀⠀⢸⣇⡠⢖⡭⠊⠀⠀⠀⠀⡄⠀
⠀⠀⠀⠀⠀⠀⢾⠭⢒⡿⠿⢿⣿⣿⣿⣿⣿⠏⠀⠸⣿⠀⣿⣿⣷⢰⣿⠀⠀⠀⣼⣿⣿⠇⠀⢀⡤⣞⠭⠚⢹⠀⠀⠀⠀⠀⠀⠇⠀
⠀⠀⠀⠀⠀⠀⢸⡀⠀⠘⡏⠒⠪⠭⣛⡿⠯⣀⡀⠀⣿⠀⣿⣿⣿⣸⡿⠀⠀⢰⣿⣿⣿⠴⣪⠕⠊⠁⠀⠀⠚⠀⠀⠀⠀⠀⢀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⡇⠀⠀⢳⠀⠀⠀⠀⠉⠑⢲⡪⠭⣛⡓⠿⢿⣿⣿⣇⠀⣀⠼⢛⡩⠒⠉⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀
⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠈⣧⠀⠀⠀⠀⠀⠀⢣⠀⠀⠀⠉⢁⡐⠖⠈⠩⠔⠊⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡎⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⡆⠀⠀⠘⣆⠀⠀⢀⡀⠠⠼⠓⠂⠩⠑⠒⠈⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⠇⠀⠀
⠀⠀⠀⠀⠀⠀⠀⣀⡙⠂⠀⠉⠉⠉⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⢱⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠂⠀⠀⠀⠀⠀⡇⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⢇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠘⡄⠀⠀⠀⢸⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡎⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠹⡀⠀⠀⠀⢇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠃⠀⠀⠀⠀⡸⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢱⡀⠀⠀⠘⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠰⠀⠀⠀⠀⢠⠃⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢣⠀⠀⠘⣳⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⡇⠀⠀⠀⢠⠃⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢇⠀⠀⢹⡆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡞⠀⠀⠀⣰⠃⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠆⠀⠀⢷⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡸⠁⠀⠀⡰⠁⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠸⡄⠀⠘⡆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣰⠃⠀⠀⡰⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠱⡀⠀⠹⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⡏⠀⠀⡰⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠑⡄⠀⢱⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⡿⠀⠀⡰⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⢆⠀⢣⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⢾⠃⠀⣰⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢦⠈⣧⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣨⠏⠀⣰⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡶⠋⠉⠓⢦⣄⢣⡈⢧⠀⠀⠀⠀⠀⠀⠀⠀⢰⡛⠀⣰⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠻⣦⣄⡀⠀⠙⢷⣷⠀⢧⠀⠀⠀⠀⠀⠀⢀⣣⡵⡾⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠛⠷⣦⣤⣹⣟⣈⣇⣀⡠⠤⠖⠛⠉⣁⣰⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⠖⠋⣉⣽⠿⢻⣿⣧⣤⣤⡶⠶⠛⠋⠁⠘⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠰⠷⠶⠛⠉⠁⢀⣿⡞⣧⠐⠀⠀⠀⢸⢸⠀⠀⢣⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣜⡟⡇⢻⡆⠀⠀⠀⠀⠏⡄⠀⠘⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢰⣿⠃⡇⠀⣿⠀⣀⠀⠀⠸⠃⠀⠀⢧⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣾⠏⠀⠃⠀⢸⡇⢸⠀⠀⠀⢀⠀⠀⠸⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⡾⠛⠦⣀⣀⠀⠀⡇⠈⡇⠀⠀⠈⡀⠀⢀⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠚⠋⠀⠀⠀⠈⢸⠀⠀⢹⠀⢣⢀⡀⠤⠒⠊⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠁⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸
Semangat sekolahnya dan harus kuliah ya nanti, kayak yg kaiu ceritain ke aku❤️.`;

const chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*()";
const output = document.getElementById("output");

function randomChar() {
    return chars[Math.floor(Math.random() * chars.length)];
}

function encrypt(text) {
    return text.split("").map(ch => ch === "\n" ? "\n" : randomChar()).join("");
}

function typeText(text, cb) {
    let i = 0, disp = "";
    function step() {
        disp += text[i++];
        output.innerHTML = disp + '<span class="cursor"></span>';
        if (i < text.length) setTimeout(step, 5);
        else cb && cb();
    }
    step();
}

function scrambleEffect(encrypted, cb) {
    let arr = encrypted.split("");
    let scrambleCount = 0;
    let scrambleTimer = setInterval(() => {
        for (let i = 0; i < arr.length; i++) {
            if (arr[i] !== "\n") arr[i] = randomChar();
        }
        output.textContent = arr.join("");
        scrambleCount++;
        if (scrambleCount > 15) {
            clearInterval(scrambleTimer);
            cb && cb();
        }
    }, 50);
}

function decryptEffect(encrypted, original) {
    let arr = encrypted.split("");
    let decryptTimer = setInterval(() => {
        let idx = Math.floor(Math.random() * arr.length);
        arr[idx] = original[idx];
        output.textContent = arr.join("");
        if (arr.join("") === original) clearInterval(decryptTimer);
    }, 5);
}

// Jalankan efeknya langsung tanpa klik
const encrypted = encrypt(message);
typeText(encrypted, () => {
    scrambleEffect(encrypted, () => {
        decryptEffect(encrypted, message);
    });
});
</script>

</body>
</html>
<!-- partial -->
  
</body>
</html>
