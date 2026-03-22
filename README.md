<!DO
<!DO
CTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Bonnie Pari 💛</title>

<style>
body{
    margin:0;
    overflow:hidden;
    background:#050617;
    font-family:'Segoe UI',sans-serif;
    color:white;
}

/* canvas estrellas */
canvas{
    position:absolute;
    top:0;
    left:0;
}

/* contenido */
.container{
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    text-align:center;
    z-index:2;
    width:80%;
}

h1{
    color:#ffd700;
    text-shadow:0 0 20px #ffd700;
}

p{
    max-width:600px;
    margin:auto;
    line-height:1.7;
    font-size:1.2em;
}

/* flores */
.flower{
    position:absolute;
    font-size:18px;
    animation:fall linear infinite;
}

@keyframes fall{
    0%{transform:translateY(-10vh);}
    100%{transform:translateY(110vh);}
}

/* botones */
button{
    margin:10px;
    padding:10px 20px;
    border:none;
    border-radius:20px;
    background:#ffd700;
    color:black;
    cursor:pointer;
    font-weight:bold;
}

/* final */
#final{
    margin-top:20px;
}
</style>
</head>

<body>

<canvas id="stars"></canvas>

<div class="container">
    <h1>🌻 Bonnie Pari 🌻</h1>

    <p>
        Como estrellas en el cielo infinito…  
        así apareciste tú en mi vida.  

        Sin avisar, sin hacer ruido,  
        pero iluminándolo todo.  

        Bonnie Pari… contigo aprendí  
        que el amor no se busca, se siente.  

        Y si el universo tuviera un lugar perfecto,  
        sería justo a tu lado 💛✨
    </p>

    <div id="final">
        <p>¿Quieres seguir conmigo? 💛</p>
        <button onclick="si()">Sí 💛</button>
        <button id="no">No 😈</button>
    </div>
</div>

<script>
/* CANVAS CONSTELACIÓN */
const canvas=document.getElementById("stars");
const ctx=canvas.getContext("2d");

canvas.width=window.innerWidth;
canvas.height=window.innerHeight;

let stars=[];
let mouse={x:null,y:null};

/* crear estrellas */
for(let i=0;i<120;i++){
    stars.push({
        x:Math.random()*canvas.width,
        y:Math.random()*canvas.height,
        vx:(Math.random()-0.5)*0.5,
        vy:(Math.random()-0.5)*0.5
    });
}

/* mouse */
window.addEventListener("mousemove",e=>{
    mouse.x=e.x;
    mouse.y=e.y;
});

/* animación */
function animate(){
    ctx.clearRect(0,0,canvas.width,canvas.height);

    stars.forEach(s=>{
        s.x+=s.vx;
        s.y+=s.vy;

        ctx.beginPath();
        ctx.arc(s.x,s.y,2,0,Math.PI*2);
        ctx.fillStyle="white";
        ctx.fill();

        stars.forEach(s2=>{
            let dx=s.x-s2.x;
            let dy=s.y-s2.y;
            let dist=Math.sqrt(dx*dx+dy*dy);

            if(dist<100){
                ctx.beginPath();
                ctx.moveTo(s.x,s.y);
                ctx.lineTo(s2.x,s2.y);
                ctx.strokeStyle="rgba(255,255,255,0.1)";
                ctx.stroke();
            }
        });
    });

    requestAnimationFrame(animate);
}
animate();

/* FLORES LLOVIENDO */
for(let i=0;i<30;i++){
    let f=document.createElement("div");
    f.className="flower";
    f.innerHTML="🌻";
    f.style.left=Math.random()*100+"vw";
    f.style.animationDuration=(5+Math.random()*5)+"s";
    document.body.appendChild(f);
}

/* BOTÓN NO QUE HUYE */
const noBtn=document.getElementById("no");

noBtn.addEventListener("mouseover",()=>{
    noBtn.style.position="absolute";
    noBtn.style.left=Math.random()*window.innerWidth+"px";
    noBtn.style.top=Math.random()*window.innerHeight+"px";
});

/* SI */
function si(){
    alert("Entonces quédate conmigo… y juntos vivamos y aguemosde esto algo bonito  ,maldita duende de mi corazon 💛✨");
}
</script>

</body>
</html>CTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Bonnie Pari 💛</title>

<style>
body{
    margin:0;
    overflow:hidden;
    background:#050617;
    font-family:'Segoe UI',sans-serif;
    color:white;
}

/* canvas estrellas */
canvas{
    position:absolute;
    top:0;
    left:0;
}

/* contenido */
.container{
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    text-align:center;
    z-index:2;
    width:80%;
}

h1{
    color:#ffd700;
    text-shadow:0 0 20px #ffd700;
}

p{
    max-width:600px;
    margin:auto;
    line-height:1.7;
    font-size:1.2em;
}

/* flores */
.flower{
    position:absolute;
    font-size:18px;
    animation:fall linear infinite;
}

@keyframes fall{
    0%{transform:translateY(-10vh);}
    100%{transform:translateY(110vh);}
}

/* botones */
button{
    margin:10px;
    padding:10px 20px;
    border:none;
    border-radius:20px;
    background:#ffd700;
    color:black;
    cursor:pointer;
    font-weight:bold;
}

/* final */
#final{
    margin-top:20px;
}
</style>
</head>

<body>

<canvas id="stars"></canvas>

<div class="container">
    <h1>🌻 Bonnie Pari 🌻</h1>

    <p>
        Como estrellas en el cielo infinito…  
        así apareciste tú en mi vida.  

        Sin avisar, sin hacer ruido,  
        pero iluminándolo todo.  

        Bonnie Pari… contigo aprendí  
        que el amor no se busca, se siente.  

        Y si el universo tuviera un lugar perfecto,  
        sería justo a tu lado 💛✨
    </p>

    <div id="final">
        <p>¿Quieres seguir conmigo? 💛</p>
        <button onclick="si()">Sí 💛</button>
        <button id="no">No 😈</button>
    </div>
</div>

<script>
/* CANVAS CONSTELACIÓN */
const canvas=document.getElementById("stars");
const ctx=canvas.getContext("2d");

canvas.width=window.innerWidth;
canvas.height=window.innerHeight;

let stars=[];
let mouse={x:null,y:null};

/* crear estrellas */
for(let i=0;i<120;i++){
    stars.push({
        x:Math.random()*canvas.width,
        y:Math.random()*canvas.height,
        vx:(Math.random()-0.5)*0.5,
        vy:(Math.random()-0.5)*0.5
    });
}

/* mouse */
window.addEventListener("mousemove",e=>{
    mouse.x=e.x;
    mouse.y=e.y;
});

/* animación */
function animate(){
    ctx.clearRect(0,0,canvas.width,canvas.height);

    stars.forEach(s=>{
        s.x+=s.vx;
        s.y+=s.vy;

        ctx.beginPath();
        ctx.arc(s.x,s.y,2,0,Math.PI*2);
        ctx.fillStyle="white";
        ctx.fill();

        stars.forEach(s2=>{
            let dx=s.x-s2.x;
            let dy=s.y-s2.y;
            let dist=Math.sqrt(dx*dx+dy*dy);

            if(dist<100){
                ctx.beginPath();
                ctx.moveTo(s.x,s.y);
                ctx.lineTo(s2.x,s2.y);
                ctx.strokeStyle="rgba(255,255,255,0.1)";
                ctx.stroke();
            }
        });
    });

    requestAnimationFrame(animate);
}
animate();

/* FLORES LLOVIENDO */
for(let i=0;i<30;i++){
    let f=document.createElement("div");
    f.className="flower";
    f.innerHTML="🌻";
    f.style.left=Math.random()*100+"vw";
    f.style.animationDuration=(5+Math.random()*5)+"s";
    document.body.appendChild(f);
}

/* BOTÓN NO QUE HUYE */
const noBtn=document.getElementById("no");

noBtn.addEventListener("mouseover",()=>{
    noBtn.style.position="absolute";
    noBtn.style.left=Math.random()*window.innerWidth+"px";
    noBtn.style.top=Math.random()*window.innerHeight+"px";
});

/* SI */
function si(){
    alert("Entonces quédate conmigo… y juntos vivamos y aguemosde esto algo bonito  ,maldita duende de mi corazon 💛✨");
}
</script>

</body>
</html>
