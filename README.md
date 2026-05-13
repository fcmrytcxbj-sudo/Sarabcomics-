<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>SarabComics</title>

<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,sans-serif;
}

body{
background:#0f0f0f;
color:white;
}

header{
background:#151515;
padding:15px 20px;
display:flex;
align-items:center;
justify-content:space-between;
position:sticky;
top:0;
z-index:1000;
border-bottom:1px solid #222;
}

.logo{
font-size:28px;
font-weight:bold;
color:#00d0ff;
}

nav{
display:flex;
gap:15px;
}

nav button{
background:none;
border:none;
color:white;
font-size:16px;
cursor:pointer;
padding:8px 14px;
border-radius:10px;
transition:0.3s;
}

nav button:hover{
background:#222;
}

.icons{
display:flex;
gap:10px;
}

.icon-btn{
width:42px;
height:42px;
border-radius:50%;
border:none;
background:#222;
color:white;
font-size:20px;
cursor:pointer;
}

.page{
display:none;
padding:30px;
}

.active{
display:block;
}

.hero{
background:linear-gradient(135deg,#001f2f,#00384f);
padding:50px;
border-radius:20px;
text-align:center;
margin-bottom:30px;
}

.hero h1{
font-size:50px;
margin-bottom:10px;
}

.hero p{
color:#ddd;
}

.comics{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
gap:20px;
}

.card{
background:#1a1a1a;
border-radius:18px;
overflow:hidden;
transition:0.3s;
box-shadow:0 0 10px rgba(0,0,0,0.5);
}

.card:hover{
transform:translateY(-5px);
}

.card img{
width:100%;
height:250px;
object-fit:cover;
}

.card-content{
padding:15px;
}

.card-content h3{
margin-bottom:10px;
}

.like-btn{
width:100%;
padding:10px;
border:none;
border-radius:12px;
background:#00b7ff;
color:white;
font-size:15px;
cursor:pointer;
}

.login-box{
max-width:400px;
margin:auto;
background:#1b1b1b;
padding:30px;
border-radius:20px;
}

.login-box h2{
margin-bottom:20px;
text-align:center;
}

.login-box input{
width:100%;
padding:12px;
margin-bottom:15px;
border:none;
border-radius:10px;
background:#2a2a2a;
color:white;
}

.login-box button{
width:100%;
padding:12px;
border:none;
border-radius:10px;
background:#00b7ff;
color:white;
font-size:16px;
cursor:pointer;
}

.verify{
background:#101010;
padding:20px;
margin:20px auto;
max-width:400px;
border-radius:15px;
text-align:center;
}

.verify button{
margin-top:15px;
padding:10px 20px;
border:none;
border-radius:10px;
background:#00b7ff;
color:white;
cursor:pointer;
}

footer{
margin-top:40px;
padding:20px;
text-align:center;
color:#888;
}
</style>
</head>
<body>

<div id="verifyPage" class="verify">
<h2>تحقق أنك إنسان 🤖</h2>
<p>اضغط الزر للدخول إلى SarabComics</p>
<button onclick="verifyHuman()">أنا لست روبوت</button>
</div>

<div id="site" style="display:none;">
<header>
<div class="logo">SarabComics</div>

<nav>
<button onclick="showPage('home')">الرئيسية</button>
<button onclick="showPage('latest')">الأحدث</button>
<button onclick="showPage('dc')">DC</button>
<button onclick="showPage('marvel')">MARVEL</button>
</nav>

<div class="icons">
<button class="icon-btn" onclick="showPage('favorites')">❤</button>
<button class="icon-btn" onclick="showPage('account')">👤</button>
</div>
</header>

<div id="home" class="page active">
<div class="hero">
<h1>مرحبًا بك في SarabComics</h1>
<p>اقرأ أفضل الكوميكس في مكان واحد. لأن البشر لا يملّون من الأبطال المقنعين الذين يعانون نفسيًا 😭</p>
</div>

<h2 style="margin-bottom:20px;">كوميكس مميزة</h2>
<div class="comics">

<div class="card">
<img src="https://images.unsplash.com/photo-1531259683007-016a7b628fc3?q=80&w=1200&auto=format&fit=crop" />
<div class="card-content">
<h3>Batman Beyond</h3>
<button class="like-btn" onclick="addFavorite('Batman Beyond')">إضافة للمفضلة</button>
</div>
</div>

<div class="card">
<img src="https://images.unsplash.com/photo-1514329926535-7f6db2f4b3b1?q=80&w=1200&auto=format&fit=crop" />
<div class="card-content">
<h3>Spider-Verse</h3>
<button class="like-btn" onclick="addFavorite('Spider-Verse')">إضافة للمفضلة</button>
</div>
</div>

</div>
</div>

<div id="latest" class="page">
<h1 style="margin-bottom:20px;">الأحدث</h1>
<div class="comics">
<div class="card">
<img src="https://images.unsplash.com/photo-1515879218367-8466d910aaa4?q=80&w=1200&auto=format&fit=crop" />
<div class="card-content">
<h3>Nightwing Issue #1</h3>
<button class="like-btn" onclick="addFavorite('Nightwing Issue #1')">إضافة للمفضلة</button>
</div>
</div>
</div>
</div>

<div id="dc" class="page">
<h1 style="margin-bottom:20px;">DC Comics</h1>
<div class="comics">
<div class="card">
<img src="https://images.unsplash.com/photo-1526374965328-7f61d4dc18c5?q=80&w=1200&auto=format&fit=crop" />
<div class="card-content">
<h3>Superman Returns</h3>
<button class="like-btn" onclick="addFavorite('Superman Returns')">إضافة للمفضلة</button>
</div>
</div>
</div>
</div>

<div id="marvel" class="page">
<h1 style="margin-bottom:20px;">Marvel Comics</h1>
<div class="comics">
<div class="card">
<img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?q=80&w=1200&auto=format&fit=crop" />
<div class="card-content">
<h3>Avengers Rise</h3>
<button class="like-btn" onclick="addFavorite('Avengers Rise')">إضافة للمفضلة</button>
</div>
</div>
</div>
</div>

<div id="favorites" class="page">
<h1 style="margin-bottom:20px;">المفضلة ❤</h1>
<div id="favoritesList"></div>
</div>

<div id="account" class="page">
<div class="login-box">
<h2>إنشاء حساب</h2>
<input type="text" id="username" placeholder="اسم المستخدم">
<input type="password" id="password" placeholder="كلمة المرور">
<button onclick="createAccount()">إنشاء الحساب</button>
<p id="accountMessage" style="margin-top:15px;text-align:center;color:#00d0ff;"></p>
</div>
</div>

<footer>
SarabComics © 2026
</footer>
</div>

<script>
function verifyHuman(){
document.getElementById('verifyPage').style.display='none';
document.getElementById('site').style.display='block';
}

function showPage(pageId){
document.querySelectorAll('.page').forEach(page=>{
page.classList.remove('active');
});

document.getElementById(pageId).classList.add('active');

if(pageId==='favorites'){
loadFavorites();
}
}

function createAccount(){
const username=document.getElementById('username').value;
const password=document.getElementById('password').value;

if(username===''||password===''){
alert('املأ جميع الحقول');
return;
}

localStorage.setItem('sarabUser',username);
document.getElementById('accountMessage').innerText='تم إنشاء الحساب بنجاح';
}

function addFavorite(comic){
let favorites=JSON.parse(localStorage.getItem('favorites'))||[];

if(!favorites.includes(comic)){
favorites.push(comic);
localStorage.setItem('favorites',JSON.stringify(favorites));
alert('تمت إضافة الكوميكس للمفضلة ❤');
}else{
alert('الكوميكس موجود بالفعل');
}
}

function loadFavorites(){
let favorites=JSON.parse(localStorage.getItem('favorites'))||[];
let container=document.getElementById('favoritesList');

container.innerHTML='';

if(favorites.length===0){
container.innerHTML='<p>لا توجد كوميكس مفضلة حاليًا</p>';
return;
}

favorites.forEach(item=>{
container.innerHTML+=`
<div style="background:#1b1b1b;padding:15px;border-radius:12px;margin-bottom:10px;">
${item}
</div>
`;
});
}
</script>

</body>
</html>
