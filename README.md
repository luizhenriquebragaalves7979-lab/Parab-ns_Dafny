<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>

<title>Parabéns Dafny 💖</title>

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    height:100vh;
    overflow:hidden;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#ffb6d9,#ff69b4,#ff1493);
    font-family:Arial, sans-serif;
    position:relative;
}

/* FUNDO BRILHANDO */

body::before{
    content:"";
    position:absolute;
    width:200%;
    height:200%;
    background:
    radial-gradient(circle,#ffffff55 1px,transparent 1px);
    background-size:40px 40px;
    animation:stars 20s linear infinite;
    z-index:0;
}

@keyframes stars{
    from{
        transform:translateY(0);
    }
    to{
        transform:translateY(100px);
    }
}

/* CONTAINER */

.container{
    text-align:center;
    color:white;
    z-index:2;
    animation:fade 2s;
    padding:20px;
}

.kitty{
    width:240px;
    animation:float 3s ease-in-out infinite;
    filter:drop-shadow(0 0 15px white);
}

h1{
    margin-top:15px;
    font-size:55px;
    text-shadow:0 0 20px white;
    animation:pulse 2s infinite;
}

p{
    margin-top:20px;
    font-size:24px;
    text-shadow:0 0 10px #fff;
    line-height:1.6;
}

/* BOTÃO */

button{
    margin-top:30px;
    padding:15px 35px;
    border:none;
    border-radius:40px;
    background:white;
    color:#ff1493;
    font-size:20px;
    font-weight:bold;
    cursor:pointer;
    box-shadow:0 0 15px white;
    transition:0.3s;
}

button:hover{
    transform:scale(1.1);
}

/* CORAÇÕES */

.heart{
    position:absolute;
    color:white;
    animation:fall linear infinite;
    z-index:1;
}

/* ANIMAÇÕES */

@keyframes pulse{
    0%{transform:scale(1);}
    50%{transform:scale(1.08);}
    100%{transform:scale(1);}
}

@keyframes float{
    0%{transform:translateY(0px);}
    50%{transform:translateY(-15px);}
    100%{transform:translateY(0px);}
}

@keyframes fall{
    0%{
        transform:translateY(-100px);
        opacity:1;
    }

    100%{
        transform:translateY(110vh);
        opacity:0;
    }
}

@keyframes fade{
    from{
        opacity:0;
        transform:scale(0.8);
    }

    to{
        opacity:1;
        transform:scale(1);
    }
}

</style>
</head>

<body>

<div class="container">

<img
class="kitty"
src="https://i.imgur.com/6M513xN.png"
alt="Hello Kitty"
/>

<h1>🎂 Parabéns Dafny 💖</h1>

<p>
Feliz aniversário meu amor 💕<br>
Que seu dia seja tão lindo quanto você ✨<br><br>

Você é muito especial pra mim 💖
</p>

<button onclick="mostrarMensagem()">
💌 Clique Aqui 💌
</button>

</div>

<!-- ÁUDIO -->

<audio id="musica" autoplay loop>
<source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<script>

/* CORAÇÕES */

function criarCoracao(){

    const heart = document.createElement("div");

    heart.classList.add("heart");

    const emojis = ["💖","💕","💗","💘","💞"];

    heart.innerHTML =
    emojis[Math.floor(Math.random()*emojis.length)];

    heart.style.left =
    Math.random()*100 + "vw";

    heart.style.animationDuration =
    Math.random()*3 + 3 + "s";

    heart.style.fontSize =
    Math.random()*20 + 20 + "px";

    document.body.appendChild(heart);

    setTimeout(()=>{
        heart.remove();
    },6000);
}

setInterval(criarCoracao,250);

/* BOTÃO */

function mostrarMensagem(){

    alert(
`💖 Dafny 💖

Você merece o melhor aniversário do mundo ✨

Te amo muitão 💕`
    );

}

/* TENTA TOCAR MÚSICA */

window.onload = () => {

    const musica =
    document.getElementById("musica");

    musica.volume = 0.5;

    musica.play().catch(()=>{
        console.log("Autoplay bloqueado");
    });

};

</script>

</body>
</html>
