<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Animal English</title>
<style>
*{box-sizing:border-box;margin:0;padding:0}
body{
  font-family:Arial,Helvetica,sans-serif;
  min-height:100vh;
  background:linear-gradient(135deg,#101827,#172b22 55%,#253b21);
  color:white;
  overflow-x:hidden;
}
header{
  height:82px;display:flex;align-items:center;justify-content:space-between;
  padding:0 32px;background:rgba(8,15,24,.78);
  border-bottom:1px solid rgba(255,255,255,.1);backdrop-filter:blur(12px);
}
.logo{font-size:26px;font-weight:900;letter-spacing:.5px}
.logo span{color:#ffd166}
.subtitle{font-size:13px;color:#b9c4c9}
.layout{display:flex;min-height:calc(100vh - 82px)}
.sidebar{
  width:290px;padding:28px 22px;background:rgba(8,15,24,.65);
  border-right:1px solid rgba(255,255,255,.09)
}
.sidebar h2{font-size:18px;margin-bottom:8px}
.sidebar p{font-size:13px;color:#aeb9bf;line-height:1.5;margin-bottom:18px}
.codebox{display:flex;gap:8px}
input{
  width:100%;padding:13px 12px;border-radius:12px;
  border:1px solid #43515a;background:#111b25;color:white;outline:none;
}
input:focus{border-color:#ffd166;box-shadow:0 0 0 3px rgba(255,209,102,.12)}
button{
  border:0;border-radius:12px;cursor:pointer;font-weight:800;
}
.unlock{padding:0 15px;background:#ffd166;color:#172018}
.unlock:hover{transform:translateY(-1px);filter:brightness(1.04)}
.status{
  margin-top:14px;padding:12px;border-radius:12px;
  background:rgba(255,255,255,.05);font-size:13px;color:#c9d1d5
}
.progress{margin-top:25px}
.progress-title{display:flex;justify-content:space-between;font-size:13px;margin-bottom:8px}
.bar{height:9px;border-radius:99px;background:#26343b;overflow:hidden}
.fill{height:100%;width:0;background:linear-gradient(90deg,#ffd166,#ff9f43);transition:.35s}
.codes{margin-top:28px}
.codes h3{font-size:14px;margin-bottom:10px}
.codes div{
  display:flex;justify-content:space-between;padding:10px 11px;
  margin-bottom:7px;border-radius:10px;background:rgba(255,255,255,.045);
  font-size:12px;color:#aeb9bf
}
.codes b{color:#ffd166}
main{flex:1;display:flex;flex-direction:column;align-items:center;padding:38px 25px}
.welcome{text-align:center;margin-bottom:22px}
.welcome h1{font-size:clamp(28px,4vw,45px);margin-bottom:8px}
.welcome p{color:#aeb9bf}
.card-area{display:flex;align-items:center;gap:18px;width:min(760px,100%)}
.arrow{
  width:52px;height:52px;flex:0 0 52px;border-radius:50%;
  background:rgba(255,255,255,.08);color:white;font-size:25px;
  border:1px solid rgba(255,255,255,.12)
}
.arrow:hover{background:rgba(255,209,102,.18);border-color:#ffd166}
.card{
  width:100%;min-height:430px;border-radius:28px;padding:25px;
  background:linear-gradient(145deg,#ff9f1c,#f57c00);
  box-shadow:0 25px 60px rgba(0,0,0,.32);
  position:relative;overflow:hidden;display:flex;flex-direction:column;
  justify-content:space-between;
}
.card:before{
  content:"";position:absolute;width:240px;height:240px;border-radius:50%;
  background:rgba(255,255,255,.12);right:-75px;top:-75px
}
.card-top{display:flex;justify-content:space-between;position:relative}
.badge{background:rgba(0,0,0,.22);padding:7px 11px;border-radius:99px;font-size:11px;font-weight:800}
.number{font-size:12px;font-weight:800;opacity:.8}
.animal{
  text-align:center;font-size:150px;line-height:1;
  filter:drop-shadow(0 15px 12px rgba(0,0,0,.18));position:relative
}
.card-info{position:relative}
.card-info h2{font-size:40px;text-align:center;margin-bottom:4px}
.card-info .scientific{text-align:center;font-style:italic;opacity:.78;margin-bottom:12px}
.facts{display:flex;gap:8px;justify-content:center;flex-wrap:wrap}
.fact{background:rgba(0,0,0,.18);padding:8px 11px;border-radius:10px;font-size:12px}
.locked{
  background:linear-gradient(145deg,#27343b,#172127);
  align-items:center;justify-content:center;text-align:center
}
.lock-icon{font-size:72px;margin-bottom:15px;opacity:.75}
.locked h2{font-size:28px;margin-bottom:8px}
.locked p{color:#aeb9bf;max-width:350px;line-height:1.5}
.hint{margin-top:18px;color:#8e9ba1;font-size:12px;text-align:center}
@media(max-width:720px){
 header{padding:0 18px;height:70px}.subtitle{display:none}
 .layout{display:block}.sidebar{width:100%;border-right:0;border-bottom:1px solid rgba(255,255,255,.09);padding:18px}
 .codes{display:none}main{padding:25px 14px}.card-area{gap:8px}.arrow{width:43px;height:43px;flex-basis:43px}
 .card{min-height:390px}.animal{font-size:120px}
}
</style>
</head>
<body>
<header>
  <div class="logo">🦁 Animal <span>English</span></div>
  <div class="subtitle">Learn English · Discover animals</div>
</header>

<div class="layout">
  <aside class="sidebar">
    <h2>🔐 Unlock a card</h2>
    <p>Enter the code you discovered in the physical game.</p>
    <div class="codebox">
      <input id="codeInput" placeholder="Example: lion01" autocomplete="off">
      <button class="unlock" onclick="unlockCard()">Unlock</button>
    </div>
    <div id="status" class="status">Try a code to discover an animal.</div>

    <div class="progress">
      <div class="progress-title"><span>Collection</span><b id="count">0 / 1</b></div>
      <div class="bar"><div id="fill" class="fill"></div></div>
    </div>

    <div class="codes">
      <h3>Available for testing</h3>
      <div><span>Lion</span><b>lion01</b></div>
    </div>
  </aside>

  <main>
    <div class="welcome">
      <h1>Animal Collection</h1>
      <p>Unlock animals and learn their English names.</p>
    </div>

    <div class="card-area">
      <button class="arrow" onclick="previousCard()">‹</button>

      <section id="card" class="card locked">
        <div class="lock-icon">🔒</div>
        <h2>Locked card</h2>
        <p>Enter a code to reveal this animal.</p>
      </section>

      <button class="arrow" onclick="nextCard()">›</button>
    </div>
    <div class="hint">💡 Tip: type <b>lion01</b> to test the first card.</div>
  </main>
</div>

<script>
const cards = [
  {
    code:"lion01",
    name:"Lion",
    emoji:"🦁",
    scientific:"Panthera leo",
    facts:["Mammal","Africa","Wild animal"],
    description:"The lion is a large wild cat known for its mane and powerful roar."
  }
];

let unlocked = new Set();
let current = 0;

function showCard(){
  const card = document.getElementById("card");
  const data = cards[current];

  if(!unlocked.has(data.code)){
    card.className="card locked";
    card.innerHTML=`
      <div class="lock-icon">🔒</div>
      <h2>Locked card</h2>
      <p>Enter the correct code to reveal this animal.</p>`;
  } else {
    card.className="card";
    card.innerHTML=`
      <div class="card-top">
        <span class="badge">UNLOCKED</span>
        <span class="number">#001</span>
      </div>
      <div class="animal">${data.emoji}</div>
      <div class="card-info">
        <h2>${data.name}</h2>
        <div class="scientific">${data.scientific}</div>
        <div class="facts">${data.facts.map(x=>`<span class="fact">${x}</span>`).join("")}</div>
      </div>`;
  }
}

function unlockCard(){
  const input=document.getElementById("codeInput");
  const code=input.value.trim().toLowerCase();
  const status=document.getElementById("status");
  const index=cards.findIndex(x=>x.code===code);

  if(index===-1){
    status.textContent="❌ Code not found. Try again.";
    status.style.color="#ffb4a2";
    return;
  }

  unlocked.add(code);
  current=index;
  status.textContent="✅ Animal unlocked!";
  status.style.color="#b8f2c8";
  input.value="";
  updateProgress();
  showCard();
}

function updateProgress(){
  document.getElementById("count").textContent=`${unlocked.size} / ${cards.length}`;
  document.getElementById("fill").style.width=(unlocked.size/cards.length*100)+"%";
}

function nextCard(){
  current=(current+1)%cards.length;
  showCard();
}
function previousCard(){
  current=(current-1+cards.length)%cards.length;
  showCard();
}

document.getElementById("codeInput").addEventListener("keydown",e=>{
  if(e.key==="Enter") unlockCard();
});

showCard();
</script>
</body>
</html>
