# para-m-a-retegui
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Para Mía 💛</title>

<style>
* {
    box-sizing: border-box;
    -webkit-tap-highlight-color: transparent;
}

html, body {
    margin: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
}

body {
    background:
        radial-gradient(circle at 50% 45%, #3b3000 0%, #171300 35%, #050505 75%);
    font-family: Georgia, serif;
    color: #ffd83d;
}

/* ---------------- INICIO ---------------- */

#inicio {
    position: fixed;
    inset: 0;
    z-index: 1000;

    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;

    background:
        radial-gradient(circle at center, #302600 0%, #0b0904 65%);

    cursor: pointer;
    transition: opacity 1.5s ease;
}

#inicio h1 {
    margin: 0;
    font-size: 30px;
    color: #ffe66b;
    text-shadow:
        0 0 10px #ffcf28,
        0 0 25px #ffb700;

    animation: latido 1.6s infinite ease-in-out;
}

#inicio p {
    margin-top: 15px;
    color: #fff3ad;
    font-size: 17px;
    opacity: .75;
}

.corazonInicio {
    margin-top: 18px;
    font-size: 38px;
    animation: latido 1.6s infinite ease-in-out;
}

@keyframes latido {
    0%,100% {
        transform: scale(1);
    }

    50% {
        transform: scale(1.12);
    }
}

/* ---------------- ESCENA ---------------- */

#escena {
    position: relative;
    width: 100vw;
    height: 100vh;
}

/* Luz detrás del corazón */

#luz {
    position: absolute;
    width: 400px;
    height: 400px;

    left: 50%;
    top: 43%;

    transform: translate(-50%, -50%);

    border-radius: 50%;

    background: radial-gradient(
        circle,
        rgba(255,215,55,.25),
        rgba(255,180,0,.08) 40%,
        transparent 70%
    );

    opacity: 0;
    transition: opacity 3s ease;

    filter: blur(10px);
}

/* ---------------- FLORES ---------------- */

#corazon {
    position: absolute;

    width: 380px;
    height: 360px;

    left: 50%;
    top: 43%;

    transform: translate(-50%, -50%);
}

.flor {
    position: absolute;

    font-size: 27px;

    opacity: 0;

    transform:
        translate(
            var(--xInicio),
            var(--yInicio)
        )
        scale(.2)
        rotate(180deg);

    transition:
        left 1.8s cubic-bezier(.17,.67,.25,1.2),
        top 1.8s cubic-bezier(.17,.67,.25,1.2),
        transform 1.8s cubic-bezier(.17,.67,.25,1.2),
        opacity .7s ease;

    filter:
        drop-shadow(0 0 3px #ffd21f)
        drop-shadow(0 0 8px #ffb700);

    user-select: none;
}

.flor.visible {
    opacity: 1;

    transform:
        translate(0,0)
        scale(1)
        rotate(0deg);
}

.flor.brillo {
    animation: brillo 2.5s infinite ease-in-out;
}

@keyframes brillo {
    0%,100% {
        filter:
            drop-shadow(0 0 3px #ffd21f)
            drop-shadow(0 0 8px #ffb700);
    }

    50% {
        filter:
            drop-shadow(0 0 8px #fff176)
            drop-shadow(0 0 22px #ffc400);
    }
}

/* ---------------- PÉTALOS ---------------- */

.petalo {
    position: fixed;

    top: -40px;

    pointer-events: none;

    z-index: 20;

    animation: caer linear forwards;

    filter: drop-shadow(0 0 5px #ffc400);
}

@keyframes caer {

    0% {
        transform:
            translateY(-40px)
            translateX(0)
            rotate(0deg);

        opacity: 0;
    }

    10% {
        opacity: 1;
    }

    50% {
        transform:
            translateY(50vh)
            translateX(40px)
            rotate(180deg);
    }

    100% {
        transform:
            translateY(110vh)
            translateX(-50px)
            rotate(360deg);

        opacity: 0;
    }
}

/* ---------------- MENSAJE ---------------- */

#mensaje {
    position: absolute;

    left: 50%;
    top: 75%;

    width: 90%;
    max-width: 560px;

    text-align: center;

    opacity: 0;

    transform:
        translate(-50%, 30px)
        scale(.95);

    transition:
        opacity 2s ease,
        transform 2s ease;

    text-shadow:
        0 0 8px #ffcf33,
        0 0 18px rgba(255,190,0,.4);
}

#mensaje.mostrar {
    opacity: 1;

    transform:
        translate(-50%,0)
        scale(1);
}

.principal {
    font-size: 25px;
    line-height: 1.55;
}

.firma {
    margin-top: 14px;

    font-size: 18px;
    line-height: 1.5;

    color: #ffe77b;
}

.corazonFinal {
    margin-top: 10px;
    font-size: 30px;

    animation: latido 1.7s infinite ease-in-out;
}

/* ---------------- ESTRELLITAS ---------------- */

.estrellita {
    position: fixed;

    pointer-events: none;

    color: #ffe66b;

    animation: desaparecer 2s forwards;

    z-index: 30;
}

@keyframes desaparecer {

    0% {
        opacity: 0;
        transform: scale(.2);
    }

    30% {
        opacity: 1;
        transform: scale(1.2);
    }

    100% {
        opacity: 0;
        transform: scale(.2);
    }
}

/* ---------------- CELULAR ---------------- */

@media (max-width: 600px) {

    #inicio h1 {
        font-size: 27px;
    }

    #inicio p {
        font-size: 16px;
    }

    #corazon {
        width: 310px;
        height: 300px;
        top: 40%;
    }

    .flor {
        font-size: 23px;
    }

    #luz {
        width: 330px;
        height: 330px;
        top: 40%;
    }

    #mensaje {
        top: 70%;
    }

    .principal {
        font-size: 20px;
    }

    .firma {
        font-size: 16px;
    }
}
</style>
</head>

<body>

<!-- PANTALLA INICIAL -->

<div id="inicio" onclick="comenzar()">

    <h1>Tocá la pantalla 💛</h1>

    <p>Tengo algo para vos...</p>

    <div class="corazonInicio">♡</div>

</div>


<!-- ESCENA -->

<div id="escena">

    <div id="luz"></div>

    <div id="corazon"></div>

    <div id="mensaje">

        <div class="principal">
            Te amo un montón, mi princesa hermosa. 💛<br>
            Es poco, pero lo hago con todo el corazón.
        </div>

        <div class="firma">
            Para Mía Rete​gui 🌻<br>
            de Nico Albornoz
        </div>

        <div class="corazonFinal">
            ♡
        </div>

    </div>

</div>


<script>

/* ----------------------------------
   POSICIONES DEL CORAZÓN
---------------------------------- */

const puntos = [

    [50,5],

    [41,8],
    [34,12],
    [28,18],
    [23,25],
    [20,33],
    [20,42],

    [23,51],
    [28,60],
    [34,68],
    [42,76],
    [50,86],

    [58,76],
    [66,68],
    [72,60],
    [77,51],

    [80,42],
    [80,33],
    [77,25],
    [72,18],
    [66,12],
    [59,8],

    [39,20],
    [32,28],
    [30,37],
    [33,46],
    [38,55],
    [44,63],

    [50,72],

    [56,63],
    [62,55],
    [67,46],
    [70,37],
    [68,28],
    [61,20],

    [45,30],
    [39,38],
    [43,47],
    [50,57],

    [57,47],
    [61,38],
    [55,30],

    [50,40]
];


/* ----------------------------------
   CREAR FLORES
---------------------------------- */

const contenedor = document.getElementById("corazon");

puntos.forEach((punto, i) => {

    const flor = document.createElement("div");

    flor.className = "flor";

    flor.innerHTML = "🌻";

    flor.style.left = punto[0] + "%";
    flor.style.top = punto[1] + "%";

    /* Lugar desde donde aparece */

    const angulo = Math.random() * Math.PI * 2;

    const distancia = 180 + Math.random() * 250;

    const x = Math.cos(angulo) * distancia;
    const y = Math.sin(angulo) * distancia;

    flor.style.setProperty("--xInicio", x + "px");
    flor.style.setProperty("--yInicio", y + "px");

    flor.style.transitionDelay =
        (i * 0.08) + "s";

    contenedor.appendChild(flor);

});


/* ----------------------------------
   COMENZAR
---------------------------------- */

function comenzar() {

    const inicio =
        document.getElementById("inicio");

    const luz =
        document.getElementById("luz");

    /* desaparecer pantalla */

    inicio.style.opacity = "0";

    setTimeout(() => {
        inicio.style.display = "none";
    }, 1500);


    /* encender luz */

    setTimeout(() => {
        luz.style.opacity = "1";
    }, 400);


    /* flores */

    const flores =
        document.querySelectorAll(".flor");

    flores.forEach((flor, i) => {

        setTimeout(() => {

            flor.classList.add("visible");

            if (i % 3 === 0) {
                flor.classList.add("brillo");
            }

        }, 500 + i * 75);

    });


    /* pétalos */

    iniciarPetalos();


    /* estrellas */

    iniciarEstrellas();


    /* mensaje */

    setTimeout(() => {

        document
            .getElementById("mensaje")
            .classList.add("mostrar");

    }, 5500);

}


/* ----------------------------------
   PÉTALOS
---------------------------------- */

function iniciarPetalos() {

    setInterval(() => {

        const petalo =
            document.createElement("div");

        petalo.className = "petalo";

        petalo.innerHTML =
            Math.random() > .45
            ? "🌻"
            : "💛";

        petalo.style.left =
            Math.random() * 100 + "vw";

        petalo.style.fontSize =
            (12 + Math.random() * 16) + "px";

        petalo.style.animationDuration =
            (5 + Math.random() * 5) + "s";

        document.body.appendChild(petalo);

        setTimeout(() => {
            petalo.remove();
        }, 11000);

    }, 400);

}


/* ----------------------------------
   ESTRELLITAS
---------------------------------- */

function iniciarEstrellas() {

    setInterval(() => {

        const estrella =
            document.createElement("div");

        estrella.className =
            "estrellita";

        estrella.innerHTML =
            Math.random() > .5
            ? "✦"
            : "♡";

        estrella.style.left =
            Math.random() * 100 + "vw";

        estrella.style.top =
            Math.random() * 85 + "vh";

        estrella.style.fontSize =
            (10 + Math.random() * 15) + "px";

        document.body.appendChild(estrella);

        setTimeout(() => {
            estrella.remove();
        }, 2000);

    }, 500);

}

</script>

</body>
</html>
