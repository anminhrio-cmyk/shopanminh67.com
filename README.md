# shopanminh67.com
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Shop Acc Blox Fruit</title>

<style>
body {
    margin: 0;
    font-family: Arial;
    background: linear-gradient(135deg, #0f172a, #1e293b);
    color: white;
    text-align: center;
}

h1 {
    padding: 20px;
    color: #facc15;
}

.shop {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
}

.card {
    background: #1e293b;
    padding: 20px;
    margin: 15px;
    border-radius: 15px;
    width: 260px;
    box-shadow: 0 0 15px rgba(0,0,0,0.5);
    transition: 0.3s;
}

.card:hover {
    transform: scale(1.05);
}

button {
    background: #f97316;
    border: none;
    padding: 12px;
    width: 100%;
    border-radius: 10px;
    cursor: pointer;
    font-weight: bold;
    color: white;
}

button:hover {
    background: red;
}

/* Popup */
.popup {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.7);
}

.popup-box {
    background: #1e293b;
    padding: 20px;
    margin: 100px auto;
    width: 300px;
    border-radius: 15px;
}
</style>

</head>

<body>

<h1>🔥 SHOP ACC BLOX FRUIT 🔥</h1>

<div class="shop">

<div class="card">
    <h2>Acc túi mù</h2>
    <p>Giá: 5.000đ</p>
    <button onclick="buy()">Mua ngay</button>
</div>

<div class="card">
    <h2>Acc VIP</h2>
    <p>Giá: 100.000đ</p>
    <button onclick="buy()">Mua ngay</button>
</div>

</div>

<!-- Popup -->
<div class="popup" id="popup">
    <div class="popup-box">
        <h2>Thanh toán</h2>
        <p>STK: <b>0987654321</b></p>
        <p>Ngân hàng: Vietcombank</p>
        <p>Tên: Nguyễn Văn A</p>
        <p>Nội dung: muaacc</p>
        <button onclick="closePopup()">Đóng</button>
    </div>
</div>

<script>
function buy() {
    document.getElementById("popup").style.display = "block";
}

function closePopup() {
    document.getElementById("popup").style.display = "none";
}
</script>

</body>
</html>
<div class="card">
    <img src="acctuytin.png.width="100%" style="border-radius:10px;">
    <h2>Acc túi mù</h2>
    <p>Giá: 5.000đ</p>
    <button onclick="buy()">Mua ngay</button>
</div>
