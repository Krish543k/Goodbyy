<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>मेरी आख़िरी बात ❤️</title>
<style>
*{margin:0;padding:0;box-sizing:border-box}
body{
  font-family:'Poppins',Arial,sans-serif;
  background:radial-gradient(circle at top,#101a3a,#030611 70%);
  color:#fff;
  min-height:100vh;
  display:flex;
  align-items:center;
  justify-content:center;
  user-select:none;
}
.container{
  width:96%;
  max-width:900px;
  min-height:75vh;
  background:rgba(255,255,255,0.04);
  border-radius:26px;
  padding:40px 28px;
  text-align:center;
  box-shadow:0 20px 60px rgba(0,0,0,0.6);
}
h1{font-size:38px;margin-bottom:14px}
.lead{opacity:.85;font-size:18px}
.btn{
  margin-top:30px;
  padding:14px 34px;
  background:#ff3b6b;
  color:#fff;
  border:0;
  border-radius:14px;
  font-size:18px;
  cursor:pointer;
}
.overlay{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.92);
  display:none;
  align-items:center;
  justify-content:center;
  z-index:99;
}
.overlay.open{display:flex}
.modal{
  background:#0b1220;
  padding:35px 30px;
  border-radius:24px;
  max-width:920px;
  width:96%;
  min-height:80vh;
  text-align:center;
  position:relative;
}
.close-btn{
  position:absolute;
  right:18px;
  top:14px;
  background:none;
  border:0;
  color:#fff;
  font-size:26px;
  cursor:pointer;
}
#page{
  font-size:20px;
  line-height:1.8;
  margin-top:30px;
  min-height:48vh;
  padding:0 16px;
  position:relative;
  overflow:hidden;
}
.nav{
  display:flex;
  justify-content:space-between;
  align-items:center;
  margin-top:20px;
}
.nav button{
  padding:10px 22px;
  border-radius:12px;
  border:0;
  background:#ff3b6b;
  color:#fff;
  font-size:16px;
}
.counter{opacity:.8;font-size:16px}
#lockScreen{display:none}
input{
  padding:12px 14px;
  border-radius:12px;
  border:0;
  font-size:18px;
  width:200px;
  text-align:center;
  margin-top:16px;
}
.heart{
  position:absolute;
  width:20px;height:20px;
  background:#ff3b6b;
  transform:rotate(45deg);
  bottom:-20px;
  animation:floatUp linear forwards;
}
.heart:before,.heart:after{
  content:'';
  position:absolute;
  width:20px;height:20px;
  background:#ff3b6b;
  border-radius:50%;
}
.heart:before{top:-10px;left:0}
.heart:after{left:-10px;top:0}
@keyframes floatUp{
  to{transform:translateY(-110vh) rotate(45deg);opacity:0}
}

/* 🔚 Final Goodbye Animation */
@keyframes goodbyeFade{
  0%{opacity:0;transform:scale(1.05)}
  20%{opacity:1}
  80%{opacity:1}
  100%{opacity:.35}
}
</style>
</head>
<body>

<audio id="bgMusic" loop>
  <source src="https://cdn.pixabay.com/download/audio/2022/11/15/audio_38c9c83894.mp3">
</audio>

<div class="container">
  <h1>मेरी आख़िरी बात ❤️</h1>
  <p class="lead">यह पेज सिर्फ तुम्हारे लिए…</p>
  <button class="btn" onclick="openLock()">Open Message 🔒</button>
</div>

<div class="overlay" id="overlay">
  <div class="modal">
    <div id="lockScreen">
      <h2>Private Message 🔐</h2>
      <input type="password" id="pwd">
      <br>
      <button class="btn" onclick="unlock()">Unlock</button>
    </div>

    <div id="content" style="display:none">
      <button class="close-btn" onclick="closeAll()">✕</button>
      <div id="page"></div>
      <div class="nav">
        <button onclick="prev()">◀ Back</button>
        <div class="counter" id="count"></div>
        <button id="nextBtn" onclick="next()">Next ▶</button>
      </div>
    </div>
  </div>
</div>

<script>
const pages=[
"Page 1","Page 2","Page 3","Page 4","Page 5","Page 6","Page 7","Page 8",
`Okk… Goodbye 💔

Milte hain agle janam me…
pakka hum ek hi caste me milenge.

Is janam me adhura reh gaya,
par agle janam me sab poora hoga.

Alvida jaana…
khud ka khayal rakhna.
Tum hamesha mere dil me rahogi.

Goodbye… 😔❤️`
];
let i=0;
const page=document.getElementById("page");
const count=document.getElementById("count");
const nextBtn=document.getElementById("nextBtn");

function openLock(){
 document.getElementById("overlay").classList.add("open");
 document.getElementById("lockScreen").style.display="block";
}
function unlock(){
 if(pwd.value==="0000"){
  lockScreen.style.display="none";
  content.style.display="block";
  render();
 }
}
function render(){
 page.innerText=pages[i];
 count.innerText=(i+1)+" / "+pages.length;
 if(i===pages.length-1){
  page.style.animation="goodbyeFade 8s ease-in-out forwards";
  nextBtn.style.display="none";
 }else{
  page.style.animation="";
  nextBtn.style.display="inline-block";
 }
}
function next(){if(i<pages.length-1){i++;render();}}
function prev(){if(i>0){i--;render();}}
function closeAll(){
 document.getElementById("overlay").classList.remove("open");
}
</script>
</body>
</html>
