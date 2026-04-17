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
    color: #facc15;
    padding: 20px;
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

.card img {
    width: 100%;
    border-radius: 12px;
    margin-bottom: 10px;
}

button {
    background: linear-gradient(45deg, orange, red);
    border: none;
    padding: 12px;
    width: 100%;
    border-radius: 10px;
    cursor: pointer;
    color: white;
    font-weight: bold;
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

    <!-- ẢNH NẰM TRÊN -->
    <img src="banner.png">

    <h2>Acc túi mù</h2>
    <p style="color:yellow;">Chỉ còn: 5.000đ</p>

    <!-- NÚT MUA NẰM DƯỚI -->
    <button onclick="buy()">Mua ngay</button>

</div>
<div class="card">
    <!-- ẢNH BẠN UPLOAD LÊN GITHUB -->
    <img src="banner.png">

    <h2>Acc túi mù</h2>
    <p style="color:yellow;">Chỉ còn: 5.000đ</p>

    <button onclick="buy()">Mua ngay</button>
</div>

</div>

<!-- Popup thanh toán -->
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
