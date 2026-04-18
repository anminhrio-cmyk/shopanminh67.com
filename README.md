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

/* Banner */
.banner img {
    width: 100%;
    height: 250px;
    object-fit: cover;
}

/* Tiêu đề */
h1 {
    color: #facc15;
    margin: 20px 0;
}

/* Shop */
.shop {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
}

/* Card */
.card {
    background: #1e293b;
    padding: 15px;
    margin: 15px;
    border-radius: 15px;
    width: 250px;
    box-shadow: 0 0 15px rgba(0,0,0,0.5);
    transition: 0.3s;
}

.card:hover {
    transform: scale(1.05);
}

/* Ảnh */
.card img {
    width: 100%;
    height: 150px;
    object-fit: cover;
    border-radius: 10px;
}

/* Nút */
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

<!-- BANNER -->
<div class="banner">
    <img src="pol.png">
</div><!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Image Zoom Popup</title>

<style>
img {
  width: 200px;
  cursor: pointer;
  border-radius: 10px;
}

/* nền mờ */
.modal {
  display: none;
  position: fixed;
  top: 0; left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.8);
  justify-content: center;
  align-items: center;
}

/* ảnh lớn */
.modal img {
  width: 500px;
  max-width: 90%;
  border-radius: 10px;
}
</style>
</head>

<body>

<img src="https://via.placeholder.com/200" onclick="openImg(this.src)">

<div class="modal" id="modal" onclick="closeImg()">
  <img id="bigImg">
</div>

<script>
function openImg(src) {
  document.getElementById("modal").style.display = "flex";
  document.getElementById("bigImg").src = src;
}

function closeImg() {
  document.getElementById("modal").style.display = "none";
}
</script>

</body>
</html>

<h1>🔥 SHOP ACC BLOX FRUIT 🔥</h1>

<!-- SHOP -->
<div class="shop">

    <!-- SẢN PHẨM -->
    <div class="card">

        <img src="accuytin.png">

        <h2>Acc túi mù</h2>
        <p style="color:yellow;">Chỉ còn: 5.000đ</p>

        <button onclick="buy()">Mua ngay</button>

    </div>

</div>

<!-- POPUP -->
<div class="popup" id="popup">
    <div class="popup-box">
        <h2>Thanh toán</h2>
        <p>STK: <b>0987654321</b></p>
        <p>Ngân hàng: ACB </p>
        <p>Tên: ĐẬU XUÂN MAI /p>
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
