<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>मेरी आख़िरी बात ❤️</title>
<style>
*{margin:0;padding:0;box-sizing:border-box}
body{
  font-family: Arial, sans-serif;
  background: radial-gradient(circle at top,#101a3a,#030611 70%);
  color:#fff;
  min-height:100vh;
  display:flex;
  align-items:center;
  justify-content:center;
}
.container{
  width:96%;
  max-width:900px;
  min-height:75vh;
  background:rgba(255,255,255,0.04);
  border-radius:26px;
  padding:40px 28px;
  text-align:center;
}
.btn{
  margin-top:30px;
  padding:14px 34px;
  background:#ff3b6b;
  color:#fff;
  border:0;
  border-radius:14px;
  font-size:18px;
}
.overlay{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.92);
  display:none;
  align-items:center;
  justify-content:center;
}
.overlay.open{display:flex}
.modal{
  background:#0b1220;
  padding:30px;
  border-radius:22px;
  width:96%;
  max-width:900px;
  min-height:80vh;
}
#page{
  font-size:20px;
  line-height:1.7;
  margin-top:25px;
}
.nav{
  display:flex;
  justify-content:space-between;
  margin-top:20px;
}
.nav button{
  padding:10px 20px;
  border:0;
  border-radius:12px;
  background:#ff3b6b;
  color:#fff;
}
@keyframes goodbyeFade{
  0%{opacity:0;transform:scale(1.08)}
  20%{opacity:1}
  80%{opacity:1}
  100%{opacity:.35;transform:scale(.95)}
}
</style>
</head>
<body>

<div class="container">
  <h1>मेरी आख़िरी बात ❤️</h1>
  <button class="btn" onclick="openMsg()">Open Message 🔒</button>
</div>

<div class="overlay" id="overlay">
  <div class="modal">
    <input id="pwd" type="password" placeholder="Password"><br><br>
    <button class="btn" onclick="unlock()">Unlock</button>

    <div id="content" style="display:none">
      <div id="page"></div>
      <div class="nav">
        <button onclick="prev()">◀ Back</button>
        <span id="count"></span>
        <button id="nextBtn" onclick="next()">Next ▶</button>
      </div>
    </div>
  </div>
</div>

<script>
const pages=[
"Page 1",
"Page 2",
"Page 3",
"Page 4",
"Page 5",
"Page 6",
"Page 7",
"Page 8",
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
function openMsg(){
 document.getElementById("overlay").classList.add("open");
}
function unlock(){
 if(pwd.value==="0000"){
  content.style.display="block";
  render();
 }
}
function render(){
 page.innerText=pages[i];
 count.innerText=(i+1)+" / "+pages.length;
 if(i===pages.length-1){
  page.style.animation="goodbyeFade 10s ease-in-out forwards";
  nextBtn.style.display="none";
 }
}
function next(){if(i<pages.length-1){i++;render();}}
function prev(){if(i>0){i--;render();}}
</script>

</body>
</html>

