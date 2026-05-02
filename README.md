# Storemoba
Moba55club store
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>mlbb55club store | Direct Topup</title>
    <style>
        body { font-family: 'Segoe UI', sans-serif; background-color: #0b0e14; color: white; text-align: center; margin: 0; padding-bottom: 50px; }
        header { background: linear-gradient(135deg, #fbbf24, #b45309); padding: 25px; border-bottom: 4px solid #000; }
        .logo-text { font-size: 28px; font-weight: 900; color: #000; }
        .input-box { background: #1a202c; padding: 20px; border-radius: 15px; max-width: 450px; margin: 20px auto; border: 1px solid #334155; }
        input { width: 42%; padding: 12px; margin: 5px; border-radius: 8px; border: 1px solid #4a5568; background: #2d3748; color: white; font-weight: bold; }
        .container { display: flex; flex-wrap: wrap; justify-content: center; gap: 15px; max-width: 1100px; margin: 0 auto; }
        .card { background: #111827; border: 2px solid #374151; border-radius: 15px; padding: 15px; width: 145px; transition: 0.3s; }
        .card:hover { border-color: #fbbf24; transform: translateY(-3px); }
        .price { font-size: 18px; font-weight: bold; color: #34d399; }
        .buy-btn { background-color: #fbbf24; color: #000; border: none; padding: 10px; width: 100%; border-radius: 8px; cursor: pointer; font-weight: bold; margin-top: 10px; }
        
        /* Payment Modal */
        #paymentModal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.98); z-index: 1000; justify-content: center; align-items: center; }
        .modal-content { background: #1f2937; padding: 25px; border-radius: 20px; width: 85%; max-width: 320px; border: 2px solid #fbbf24; }
        
        /* QR Code Styling - Improved */
        .qr-container { background: white; padding: 10px; border-radius: 15px; margin: 15px auto; width: 220px; height: 220px; display: flex; align-items: center; justify-content: center; }
        .qr-container img { width: 100%; height: auto; display: block; }
        
        .confirm-btn { background-color: #22c55e; color: white; border: none; padding: 15px; width: 100%; border-radius: 10px; cursor: pointer; font-weight: bold; font-size: 16px; margin-top: 10px; }
    </style>
</head>
<body>

<header>
    <div class="logo-text">MLBB55CLUB STORE</div>
    <p style="color: #000; font-weight: bold;">Fast & Secure Topup</p>
</header>

<div class="input-box">
    <h3>Enter Details</h3>
    <input type="number" id="uid" placeholder="User ID">
    <input type="number" id="sid" placeholder="Zone ID">
</div>

<div class="container">
    <div class="card" style="border-color: #fbbf24;">
        <div style="font-size: 25px;">🎫</div>
        <div class="pack-name">Weekly Pass</div>
        <div class="price">₹175</div>
        <button onclick="pay('Weekly Pass', '175')" class="buy-btn">BUY NOW</button>
    </div>
    <div class="card">
        <div style="font-size: 25px;">💎</div>
        <div class="pack-name">86 Diamonds</div>
        <div class="price">₹149</div>
        <button onclick="pay('86 Gems', '149')" class="buy-btn">BUY</button>
    </div>
    <div class="card">
        <div style="font-size: 25px;">💎</div>
        <div class="pack-name">172 Diamonds</div>
        <div class="price">₹295</div>
        <button onclick="pay('172 Gems', '295')" class="buy-btn">BUY</button>
    </div>
    <div class="card">
        <div style="font-size: 25px;">💎</div>
        <div class="pack-name">257 Diamonds</div>
        <div class="price">₹442</div>
        <button onclick="pay('257 Gems', '442')" class="buy-btn">BUY</button>
    </div>
</div>

<div id="paymentModal">
    <div class="modal-content">
        <h3 style="color: #fbbf24;">Scan to Pay</h3>
        <p>Amount: <b id="payAmt" style="color:#34d399;"></b></p>
        
        <div class="qr-container">
            <img src="https://i.ibb.co/v4S8L8m/1000131026.jpg" alt="Payment QR" onerror="this.src='https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=upi://pay?pa=7501671440@paytm&pn=Sonu&am=' + p">
        </div>

        <p style="font-size: 11px; color: #9ca3af;">QR शो न होने पर 7501671440 पर पे करें।</p>
        <button onclick="send()" class="confirm-btn">I HAVE PAID ✅</button>
        <p onclick="closeM()" style="cursor:pointer; margin-top:15px; color:#9ca3af;">[ Cancel ]</p>
    </div>
</div>

<script>
    let n, p;
    function pay(name, price) {
        let u = document.getElementById('uid').value;
        if(!u) { alert("ID bhariye!"); return; }
        n = name; p = price;
        document.getElementById('payAmt').innerText = "₹" + price;
        document.getElementById('paymentModal').style.display = "flex";
    }
    function closeM() { document.getElementById('paymentModal').style.display = "none"; }
    function send() {
        let u = document.getElementById('uid').value;
        let s = document.getElementById('sid').value;
        let msg = `🔥 *MLBB55CLUB ORDER* 🔥\nPack: ${n}\nPrice: ₹${p}\nID: ${u} (${s})\nStatus: Paid`;
        window.location.href = `https://wa.me/917501671440?text=${encodeURIComponent(msg)}`;
    }
</script>
</body>
</html>
