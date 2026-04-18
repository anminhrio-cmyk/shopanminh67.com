# shopanminh67.com
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Shop Blox Fruit VIP</title>

<style>
body {
    margin: 0;
    font-family: Arial;
    background: #0b1220;
    color: white;
}

header {
    background: #1e293b;
    padding: 20px;
    text-align: center;
    font-size: 22px;
    font-weight: bold;
}

.cart-box {
    position: fixed;
    right: 20px;
    top: 20px;
    background: #22c55e;
    padding: 10px 15px;
    border-radius: 10px;
    cursor: pointer;
    font-weight: bold;
}

/* MENU 2 MỤC */
.menu {
    display: flex;
    justify-content: center;
    margin-top: 20px;
    gap: 20px;
}

.tab {
    padding: 10px 20px;
    background: #1e293b;
    border-radius: 10px;
    cursor: pointer;
    font-weight: bold;
}

.tab.active {
    background: #22c55e;
}

/* PRODUCT */
.container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    margin-top: 20px;
}

.card {
    background: #1e293b;
    width: 260px;
    margin: 15px;
    padding: 15px;
    border-radius: 12px;
    text-align: center;
}

.price {
    color: #22c55e;
    font-weight: bold;
}

button {
    background: #22c55e;
    border: none;
    padding: 10px;
    width: 100%;
    border-radius: 8px;
    cursor: pointer;
    font-weight: bold;
}

button:hover {
    background: #16a34a;
}

/* CART */
.cart-panel {
    position: fixed;
    right: -340px;
    top: 0;
    width: 320px;
    height: 100%;
    background: #111827;
    padding: 15px;
    transition: 0.3s;
    overflow-y: auto;
}

.cart-panel.open {
    right: 0;
}

.cart-item {
    background: #1e293b;
    padding: 10px;
    margin-bottom: 10px;
    border-radius: 8px;
}

.remove {
    background: red;
    margin-top: 5px;
    border: none;
    padding: 5px;
    color: white;
    cursor: pointer;
    border-radius: 5px;
}

.total {
    margin-top: 15px;
    font-size: 18px;
    font-weight: bold;
}

.pay-box {
    background: #0f172a;
    padding: 10px;
    margin-top: 10px;
    border-radius: 10px;
    display: none;
}
</style>
</head>

<body>

<header>
🥭 SHOP BLOX FRUIT VIP - UY TÍN
</header>

<div class="cart-box" onclick="toggleCart()">
🛒 Giỏ: <span id="count">0</span>
</div>

<!-- MENU 2 MỤC -->
<div class="menu">
    <div class="tab active" onclick="show('random')">🎲 Acc Random VIP 5K</div>
    <div class="tab" onclick="show('select')">👑 Acc Tự Chọn VIP</div>
</div>

<!-- RANDOM -->
<div class="container" id="random">

    <div class="card">
        <h3>🎲 Acc Random VIP</h3>
        <p class="price">5.000đ / 1 acc</p>
        <button onclick="add('Acc Random VIP', 5000)">Mua Random</button>
    </div>

</div>

<!-- SELECT -->
<div class="container" id="select" style="display:none">

    <div class="card">
        <h3>👑 Acc Full Fruit</h3>
        <p class="price">50.000đ</p>
        <button onclick="add('Acc Full Fruit VIP', 50000)">Thêm giỏ</button>
    </div>

    <div class="card">
        <h3>👑 Acc Yoru + Dragon</h3>
        <p class="price">120.000đ</p>
        <button onclick="add('Acc Yoru Dragon VIP', 120000)">Thêm giỏ</button>
    </div>

</div>

<!-- CART -->
<div class="cart-panel" id="cart">
    <h2>🛒 Giỏ hàng</h2>
    <div id="items"></div>

    <div class="total">
        Tổng: <span id="total">0</span>đ
    </div>

    <button onclick="showPay()">💳 Thanh toán</button>

    <div class="pay-box" id="payBox">
        <h3>💳 MOMO / NGÂN HÀNG</h3>
        <p><b>Momo:</b> 0901234567</p>
        <p><b>Bank:</b> ACB Bank</p>
        <p><b>STK:</b> 123456789</p>
        <p><b>Chủ TK:</b> SHOP BLOX FRUIT</p>
    </div>
</div>

<script>
let cart = [];

function add(name, price) {
    cart.push({name, price});
    update();
}

function update() {
    let items = document.getElementById("items");
    let count = document.getElementById("count");
    let total = document.getElementById("total");

    items.innerHTML = "";
    let sum = 0;

    cart.forEach((i, index) => {
        sum += i.price;

        items.innerHTML += `
        <div class="cart-item">
            <b>${i.name}</b><br>
            ${i.price.toLocaleString()}đ
            <button class="remove" onclick="removeItem(${index})">Xóa</button>
        </div>
        `;
    });

    count.innerText = cart.length;
    total.innerText = sum.toLocaleString();
}

function removeItem(i) {
    cart.splice(i, 1);
    update();
}

function toggleCart() {
    document.getElementById("cart").classList.toggle("open");
}

function show(type) {
    document.getElementById("random").style.display = type === "random" ? "flex" : "none";
    document.getElementById("select").style.display = type === "select" ? "flex" : "none";
}

function showPay() {
    document.getElementById("payBox").style.display = "block";
}
</script>

</body>
</html>
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Shop Blox Fruit VIP</title>

<style>
body {
    margin: 0;
    font
