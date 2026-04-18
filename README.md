# shopanminh67.com
<script>

let cart = [];
let sheetAccounts = [];

// 🔗 GOOGLE SHEET LINK
const SHEET_URL = "https://opensheet.elk.sh/YOUR_SHEET_ID/Sheet1";

// 📦 lưu acc đã bán (local)
let soldAccounts = JSON.parse(localStorage.getItem("soldAcc")) || [];

// 📥 LOAD ACC
async function loadAccounts() {
    try {
        let res = await fetch(SHEET_URL);
        sheetAccounts = await res.json();
        console.log("Loaded:", sheetAccounts);
    } catch (e) {
        console.log("Error load sheet");
    }
}

// 🎲 LẤY ACC CHƯA BÁN
function getRandomAcc() {

    // lọc acc chưa bán
    let available = sheetAccounts.filter(acc => {
        return !soldAccounts.includes(acc.user);
    });

    if (available.length === 0) {
        return {user: "HẾT ACC", pass: "NO DATA"};
    }

    let acc = available[Math.floor(Math.random() * available.length)];

    return acc;
}

// 💾 đánh dấu đã bán
function markSold(user) {
    soldAccounts.push(user);
    localStorage.setItem("soldAcc", JSON.stringify(soldAccounts));
}

function add(name, price) {

    if (name === "Acc Random VIP") {

        let acc = getRandomAcc();

        alert(
`🎉 ACC CỦA BẠN:
👤 User: ${acc.user}
🔑 Pass: ${acc.pass}`
        );

        // ❗ đánh dấu đã bán
        markSold(acc.user);

        cart.push({
            name: `Acc Random VIP (${acc.user})`,
            price: 5000
        });

    } else {
        cart.push({name, price});
    }

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

// 🚀 load sheet
loadAccounts();

</script>
