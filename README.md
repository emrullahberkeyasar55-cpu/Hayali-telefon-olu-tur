# Hayalinizdeki-telefonu-olusturun
Kendi hayalinizdeki telefonu oluşturun
index.html

<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>Ultimate Phone Builder</title>
<style>
body{
margin:0;
font-family:Arial;
background:linear-gradient(135deg,#000428,#004e92);
color:white;
}
.container{max-width:1100px;margin:auto;padding:20px;}
h1{text-align:center;}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:20px;}
.card{
background:rgba(0,0,0,0.55);
padding:20px;
border-radius:16px;
}
select,button{
width:100%;
padding:10px;
margin-top:5px;
border-radius:10px;
border:none;
}
button{
background:#00ffc8;
font-size:18px;
cursor:pointer;
}
.phone{
width:220px;
height:420px;
margin:20px auto;
border-radius:35px;
background:black;
box-shadow:0 0 40px rgba(0,255,200,0.7);
transition:0.4s;
}
.bar{
height:14px;
background:#333;
border-radius:10px;
overflow:hidden;
margin:5px 0;
}
.fill{
height:100%;
background:#00ffc8;
width:0%;
transition:0.5s;
}
.lang{
text-align:right;
margin-bottom:10px;
}
</style>
</head>

<body>
<div class="container">

<div class="lang">
<button onclick="setLang('tr')">TR</button>
<button onclick="setLang('en')">EN</button>
</div>

<h1 id="title">📱 Ultimate Telefon Oluşturucu</h1>

<div class="phone" id="phone"></div>

<div class="grid">

<div class="card">
<h3 id="design">Tasarım</h3>

<label>Kasa</label>
<select id="kasa">
<option value="2000">Cam</option>
<option value="3000">Alüminyum</option>
<option value="4500">Titanyum</option>
<option value="3500">Deri</option>
</select>

<label>Renk</label>
<select id="renk">
<option value="black">Siyah</option>
<option value="silver">Gümüş</option>
<option value="blue">Mavi</option>
<option value="purple">Mor</option>
</select>

<label>Ekran</label>
<select id="ekran">
<option value="3000">FHD+ 120Hz</option>
<option value="4500">QHD+ 144Hz</option>
<option value="6000">4K 165Hz</option>
</select>
</div>

<div class="card">
<h3 id="hardware">Donanım</h3>

<label>İşlemci</label>
<select id="cpu">
<option value="8000">Snapdragon 8 Gen 4</option>
<option value="7000">Dimensity 9400</option>
<option value="9000">Apple M-Phone Ultra</option>
</select>

<label>RAM</label>
<select id="ram">
<option value="2000">12 GB</option>
<option value="3500">16 GB</option>
<option value="5000">24 GB</option>
</select>

<label>Depolama</label>
<select id="storage">
<option value="2000">256 GB</option>
<option value="3500">512 GB</option>
<option value="6000">1 TB</option>
</select>

<label>Kamera</label>
<select id="kamera">
<option value="3000">108 MP</option>
<option value="5000">200 MP</option>
<option value="8000">1'' Sensor Pro</option>
</select>

<label>Batarya</label>
<select id="batarya">
<option value="2500">5000 mAh</option>
<option value="4000">6000 mAh</option>
<option value="6000">7000 mAh</option>
</select>
</div>

</div>

<button onclick="olustur()">🚀 Telefonu Oluştur</button>

<div class="card">
<h3 id="performance">Performans</h3>
<p>AnTuTu</p>
<div class="bar"><div class="fill" id="antutuBar"></div></div>
<p>Geekbench</p>
<div class="bar"><div class="fill" id="geekBar"></div></div>
</div>

<div class="card" id="sonuc"></div>

<button onclick="exportJSON()">📦 Yapıyı Dışa Aktar</button>

</div>

<script>
let lang="tr";

function setLang(l){
lang=l;
document.getElementById("title").innerText=l=="tr"?"📱 Ultimate Telefon Oluşturucu":"📱 Ultimate Phone Builder";
}

function olustur(){
let total=0;
document.querySelectorAll("select").forEach(s=>total+=Number(s.value));

let antutu=Math.min(100,Math.round(total/400));
let geek=Math.min(100,Math.round(total/500));

document.getElementById("antutuBar").style.width=antutu+"%";
document.getElementById("geekBar").style.width=geek+"%";

let renk=document.getElementById("renk").value;
document.getElementById("phone").style.background=renk;

document.getElementById("sonuc").innerHTML=`
💰 Fiyat: <b>${total} TL</b><br>
🎮 AnTuTu: <b>${antutu}/100</b><br>
⚡ Geekbench: <b>${geek}/100</b>
`;
}

function exportJSON(){
let data={};
document.querySelectorAll("select").forEach(s=>data[s.id]=s.options[s.selectedIndex].text);
alert(JSON.stringify(data,null,2));
}
</script>

</body>
</html>

<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>Phone Lab X</title>
<style>
body{
margin:0;
font-family:Arial;
background:linear-gradient(135deg,#020024,#090979,#00d4ff);
color:white;
}
.container{max-width:1200px;margin:auto;padding:20px;}
h1{text-align:center;}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:20px;}
.card{
background:rgba(0,0,0,0.55);
padding:20px;
border-radius:18px;
}
select,input,button{
width:100%;
padding:10px;
margin-top:6px;
border-radius:10px;
border:none;
}
button{
background:#00ffc8;
font-size:17px;
cursor:pointer;
}
.phone-wrap{
display:flex;
justify-content:center;
margin:20px 0;
perspective:1000px;
}
.phone{
width:230px;
height:450px;
border-radius:40px;
background:black;
box-shadow:0 20px 50px rgba(0,0,0,0.8);
transition:0.3s;
}
.phone:hover{
transform:rotateY(10deg) rotateX(5deg);
}
.bar{
height:14px;
background:#333;
border-radius:10px;
overflow:hidden;
}
.fill{
height:100%;
background:#00ffc8;
width:0%;
transition:0.5s;
}
.logo{
width:90px;
height:90px;
border-radius:50%;
background:#00ffc8;
color:black;
display:flex;
align-items:center;
justify-content:center;
font-size:32px;
margin:auto;
font-weight:bold;
}
.lang{text-align:right;}
</style>
</head>

<body>
<div class="container">

<div class="lang">
<button onclick="setLang('tr')">TR</button>
<button onclick="setLang('en')">EN</button>
</div>

<h1 id="title">📱 PHONE LAB X</h1>

<div class="card">
<h3>Marka</h3>
<input id="brand" placeholder="Marka adı gir">
<div class="logo" id="logo">X</div>
</div>

<div class="phone-wrap">
<div class="phone" id="phone"></div>
</div>

<div class="grid">

<div class="card">
<h3>Tasarım</h3>
<select id="kasa">
<option value="2000">Cam</option>
<option value="3000">Alüminyum</option>
<option value="4500">Titanyum</option>
<option value="3500">Deri</option>
</select>

<select id="renk">
<option value="black">Siyah</option>
<option value="silver">Gümüş</option>
<option value="blue">Mavi</option>
<option value="purple">Mor</option>
</select>

<select id="ekran">
<option value="3000">FHD+ 120Hz</option>
<option value="4500">QHD+ 144Hz</option>
<option value="6500">4K 165Hz</option>
</select>
</div>

<div class="card">
<h3>Donanım</h3>
<select id="cpu">
<option value="8000">Snapdragon 8 Gen 4</option>
<option value="7000">Dimensity 9400</option>
<option value="9000">M-Phone Ultra</option>
</select>

<select id="ram">
<option value="2000">12 GB RAM</option>
<option value="3500">16 GB RAM</option>
<option value="5000">24 GB RAM</option>
</select>

<select id="storage">
<option value="2000">256 GB</option>
<option value="3500">512 GB</option>
<option value="6000">1 TB</option>
</select>

<select id="kamera">
<option value="3000">108 MP</option>
<option value="5500">200 MP</option>
<option value="8500">1'' Sensor Pro</option>
</select>

<select id="batarya">
<option value="2500">5000 mAh</option>
<option value="4000">6000 mAh</option>
<option value="6500">7000 mAh</option>
</select>
</div>

</div>

<button onclick="olustur()">🚀 Telefonu Oluştur</button>

<div class="card">
<h3>Performans</h3>
AnTuTu
<div class="bar"><div class="fill" id="antutu"></div></div>
Geekbench
<div class="bar"><div class="fill" id="geek"></div></div>
<p id="ai"></p>
</div>

<button onclick="exportJSON()">📦 Yapıyı Dışa Aktar</button>

</div>

<script>
function setLang(l){
document.getElementById("title").innerText=
l=="tr"?"📱 PHONE LAB X":"📱 PHONE LAB X";
}

document.getElementById("brand").oninput=function(){
let t=this.value;
document.getElementById("logo").innerText=t?t[0].toUpperCase():"X";
}

function olustur(){
let total=0;
document.querySelectorAll("select").forEach(s=>total+=Number(s.value));

let antutu=Math.min(100,Math.round(total/380));
let geek=Math.min(100,Math.round(total/480));

document.getElementById("antutu").style.width=antutu+"%";
document.getElementById("geek").style.width=geek+"%";

let renk=document.getElementById("renk").value;
document.getElementById("phone").style.background=renk;

let aiText="";

if(antutu>85) aiText="🔥 Bu telefon hardcore oyuncular ve güç kullanıcıları için.";
else if(antutu>65) aiText="⚡ Bu telefon günlük kullanım + oyun için ideal.";
else aiText="📱 Bu telefon uzun pil ve stabilite odaklı.";

document.getElementById("ai").innerText=aiText;
}

function exportJSON(){
let data={};
document.querySelectorAll("select").forEach(s=>{
data[s.id]=s.options[s.selectedIndex].text;
});
alert(JSON.stringify(data,null,2));
}
</script>

</body>
</html>

Puan =
(Yıldız Ortalaması × 20)
+ (Donanım Skoru × 0.35)
+ (Yorum Etkisi)

import { initializeApp } from "firebase/app";
import { getAuth } from "firebase/auth";
import { getFirestore } from "firebase/firestore";

const firebaseConfig = {
  apiKey: "API_KEY",
  authDomain: "xxx.firebaseapp.com",
  projectId: "xxx",
};

export const app = initializeApp(firebaseConfig);
export const auth = getAuth(app);
export const db = getFirestore(app);

if(!auth.currentUser){
  alert("Telefon sunmak için kayıt olmalısın");
  return;
}

const realPhones = [
{
 id:"pro1",
 name:"Premium Amiral",
 cpu:"Snapdragon 8 Gen 3",
 camera:"200 MP",
 ram:"12 GB",
 battery:"5000 mAh"
},
{
 id:"mid1",
 name:"Orta Seviye",
 cpu:"Snapdragon 7+",
 camera:"64 MP",
 ram:"8 GB",
 battery:"5000 mAh"
}
];

/public
 ├── index.html
 ├── firebase.js
 ├── auth.js
 ├── sun.js
 ├── style.css
