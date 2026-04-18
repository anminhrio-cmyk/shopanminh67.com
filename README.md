# shopanminh67.com
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Shop Blox Fruit PRO MAX</title>

<style>
body{
    margin:0;
    font-family:Arial;
    background:#0b1220;
    color:white;
}

header{
    background:#1e293b;
    padding:18px;
    text-align:center;
    font-size:22px;
    font-weight:bold;
}

.cart-box{
    position:fixed;
    right:20px;
    top:20px;
    background:#22c55e;
    padding:10px 15px;
    border-radius:10px;
    cursor:pointer;
    font-weight:bold;
}

/* MENU */
.menu{
    display:flex;
    justify-content:center;
    gap:15px;
    margin-top:15px;
}

.tab{
    background:#1e293b;
    padding:10px 15px;
    border-radius:10px;
    cursor:pointer;
}

.tab.active{background:#22c55e}

/* SHOP */
.container{
    display:flex;
    justify-content:center;
    flex-wrap:wrap;
    margin-top:20px;
}

.card{
    background:#1e293b;
    width:260px;
    margin:15px;
    padding:15px;
    border-radius:12px;
    text-align:center;
}

.price{color:#22c55e;font-weight:bold}

button{
    width:100%;
    padding:10px;
    border:none;
    background:#22c55e;
    font-weight:bold;
    cursor:pointer;
    border-radius:8px;
}

/* CART */
.cart-panel{
    position:fixed;
    right:-340px;
    top:0;
    width:320px;
    height:100%;
    background:#111827;
    padding:15px;
    transition:0.3s;
    overflow-y:auto;
}

.cart-panel.open{right:0}

.cart-item{
    background:#1e293b;
    padding:10px;
    margin-bottom:10px;
    border-radius:8px;
}

.remove{
    background:red;
    border:none;
    color:white;
    padding:5px;
    border-radius:5px;
}

/* PAY */
.pay-box{
    background:#0f172a;
    padding:10px;
    margin-top:10px;
    border-radius:10px;
}

.qr{
    width:200px;
    border-radius:10px;
}

/* ADMIN */
.admin{
    display:none;
    background:#111827;
    padding:10px;
    margin:10px;
    border-radius:10px;
}
</style>
</head>

<body>

<header>🥭 SHOP BLOX FRUIT PRO MAX</header>

<div class="cart-box" onclick="toggleCart()">
🛒 <span id="count">0</span>
</div>

<!-- MENU -->
<div class="menu">
    <div class="tab active" onclick="show('shop')">SHOP</div>
    <div class="tab" onclick="toggleAdmin()">ADMIN</div>
</div>

<!-- SHOP -->
<div class="container" id="shop">

    <div class="card">
        <h3>🎁 ACC TÚI MÙ</h3>
        <p class="price">5.000đ</p>
        <button onclick="add('Acc Túi Mù',5000)">MUA</button>
    </div>

    <div class="card">
        <h3>🍑 ACC MOCHI 100%</h3>
        <p class="price">20.000đ</p>
        <button onclick="add('Acc Mochi 100%',20000)">MUA</button>
    </div>

    <div class="card">
        <h3>🦊 ACC KITSUNE 100%</h3>
        <p class="price">80.000đ</p>
        <button onclick="add('Acc Kitsune 100%',80000)">MUA</button>
    </div>

</div>

<!-- CART -->
<div class="cart-panel" id="cart">

<h2>🛒 GIỎ HÀNG</h2>

<div id="items"></div>

<p><b>Tổng:</b> <span id="total">0</span>đ</p>

<button onclick="pay()">💳 THANH TOÁN</button>

<div class="pay-box" id="payBox" style="display:none;">
    <h3>💳 THANH TOÁN</h3>

    <p>Momo: 0901234567</p>
    <p>MB Bank: 123456789</p>

    <div style="text-align:center;">
        <img id="qr" class="qr" src="">
    </div>

    <p id="status" style="color:#22c55e;"></p>
</div>

</div>

<!-- ADMIN -->
<div class="admin" id="admin">

<h3>🔐 ADMIN PANEL</h3>

<input id="name" placeholder="Tên acc"><br><br>
<input id="price" placeholder="Giá"><br><br>

<button onclick="addAdmin()">Thêm Acc</button>

<div id="adminList"></div>

</div>

<script>

let cart=[];
let kho=[
    {name:"Acc Túi Mù",price:5000},
    {name:"Acc Mochi 100%",price:20000},
    {name:"Acc Kitsune 100%",price:80000}
];

// 👉 SHOP
function add(name,price){
    cart.push({name,price});
    update();
}

function update(){
    let items=document.getElementById("items");
    let count=document.getElementById("count");
    let total=document.getElementById("total");

    items.innerHTML="";
    let sum=0;

    cart.forEach((i,index)=>{
        sum+=i.price;

        items.innerHTML+=`
        <div class="cart-item">
        ${i.name}<br>${i.price}đ
        <button class="remove" onclick="del(${index})">X</button>
        </div>`;
    });

    count.innerText=cart.length;
    total.innerText=sum;
}

function del(i){
    cart.splice(i,1);
    update();
}

function toggleCart(){
    document.getElementById("cart").classList.toggle("open");
}

// 💳 QR TỰ ĐỔI THEO TIỀN
function pay(){
    let total=cart.reduce((a,b)=>a+b.price,0);

    document.getElementById("payBox").style.display="block";

    let qr=`https://img.vietqr.io/image/mbbank-123456789-compact.png?amount=${total}&addInfo=BloxFruit`;

    document.getElementById("qr").src=qr;

    setTimeout(()=>{
        document.getElementById("status").innerText="✔ ĐÃ NHẬN TIỀN (DEMO)";
    },2000);
}

// 📦 ADMIN
function toggleAdmin(){
    let a=document.getElementById("admin");
    a.style.display=a.style.display==="block"?"none":"block";
    renderAdmin();
}

function addAdmin(){
    let n=document.getElementById("name").value;
    let p=parseInt(document.getElementById("price").value);

    kho.push({name:n,price:p});
    renderAdmin();
}

function renderAdmin(){
    let box=document.getElementById("adminList");
    box.innerHTML="";

    kho.forEach((i)=>{
        box.innerHTML+=`<p>${i.name} - ${i.price}đ</p>`;
    });
}

</script>

</body>
</html>
