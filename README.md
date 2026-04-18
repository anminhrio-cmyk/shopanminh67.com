# shopanminh67.com
HTML
<script>
let cart = [];

// 🎲 DANH SÁCH ACC (có user + pass)
let randomAccounts = [
    {user: "BloxUser001", pass: "Pass1234"},
    {user: "DragonKing99", pass: "Mochi777"},
    {user: "YoruMasterX", pass: "DarkBlade88"},
    {user: "KitsuneGod01", pass: "Fox9999"},
    {user: "BuddhaTank77", pass: "TankPro55"}
];

function add(name, price) {

    // 🎲 ACC RANDOM VIP 5K
    if (name === "Acc Random VIP") {

        let acc = randomAccounts[Math.floor(Math.random() * randomAccounts.length)];

        let accInfo = `
🎉 ACC CỦA BẠN:
👤 User: ${acc.user}
🔑 Pass: ${acc.pass}
        `;

        alert(accInfo);

        cart.push({
            name: `Acc Random VIP (${acc.user})`,
            price: 5000
        });

    } 
    else {
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
</script>
