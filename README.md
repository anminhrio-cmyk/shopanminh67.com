# shopanminh67.com
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Shop Acc Blox Fruit - Uy Tín</title>

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

/* MENU */
.menu {
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-top: 20px;
}

.tab {
    background: #1e293b;
    padding: 10px 20px;
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
    justify-content: center;
    flex-wrap: wrap;
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

.pay {
    background: #3b82f6;
    margin-top: 10px;
}
</style>
</head>

<body>

<header>
🥭 SHOP ACC BLOX FRUIT - UY TÍN GIÁ RẺ
</header>

<div class="cart-box" onclick="toggleCart()">
🛒 Giỏ: <span id="count">0</span>
</div>

<!-- MENU -->
<div class="menu">
    <div class="tab active" onclick="show('blind')">🎁 Acc Túi Mù</div>
    <div class="tab" onclick="show('select')">👑 Acc Tự Chọn</div>
</div>

<!-- TÚI MÙ -->
<div class="container" id="blind">

    <div class="card">
        <h3>🎁 ACC TÚI MÙ</h3>
        <p class="price">5.000đ</p>
        <p>Random acc Blox Fruit</p>
        <button onclick="add('Acc Túi Mù', 5000)">MUA NGAY</button>
    </div>

</div>

<!-- TỰ CHỌN -->
<div class="container" id="select" style="display:none">

    <div class="card">
        <h3>🍑 ACC MOCHI 100%</h3>
        <p class="price">20.000đ</p>
        <p>Acc chắc chắn có Mochi</p>
        <button onclick="add('Acc Mochi 100%', 20000)">MUA NGAY</button>
    </div>

    <div class="card">
        <h3>🦊 ACC KITSUNE 100%</h3>
        <p class="price">80.000đ</p>
        <p>Acc chắc chắn có Kitsune</p>
        <button onclick="add('Acc Kitsune 100%', 80000)">MUA NGAY</button>
    </div>

</div>

<!-- CART -->
<div class="cart-panel" id="cart">
    <h2>🛒 Giỏ hàng</h2>
    <div id="items"></div>

    <div class="total">
        Tổng: <span id="total">0</span>đ
    </div>

    <button class="pay" onclick="alert('Thanh toán demo: Momo 0901234567')">
        💳 Thanh toán
    </button>
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
    document.getElementById("blind").style.display = type === "blind" ? "flex" : "none";
    document.getElementById("select").style.display = type === "select" ? "flex" : "none";
}
</script>

</body>
</html>
