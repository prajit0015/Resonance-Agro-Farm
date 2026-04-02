<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Resonance Agro Farm</title>

<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #f7fff5;
}

/* Header */
header {
    background: #2d6a4f;
    color: white;
    padding: 20px;
    text-align: center;
    font-size: 28px;
    font-weight: bold;
}

/* Hero Image */
.hero {
    background: url('https://images.unsplash.com/photo-1500595046743-cd271d694d30?auto=format&fit=crop&w=1500&q=60') center/cover no-repeat;
    height: 350px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    font-size: 40px;
    font-weight: bold;
    text-shadow: 2px 2px 5px black;
}

/* Sections */
.section {
    padding: 40px;
    text-align: center;
}

.products {
    display: flex;
    justify-content: center;
    gap: 25px;
    flex-wrap: wrap;
}

.product-card {
    background: white;
    padding: 20px;
    width: 260px;
    border-radius: 12px;
    box-shadow: 0 3px 8px rgba(0,0,0,0.2);
}

.product-card img {
    width: 100%;
    border-radius: 10px;
}

/* Contact Box */
.contact-box {
    background: #d8f3dc;
    padding: 30px;
    border-radius: 15px;
    width: 90%;
    max-width: 500px;
    margin: auto;
    box-shadow: 0 3px 8px rgba(0,0,0,0.2);
}

.contact-box input, 
.contact-box textarea, 
.contact-box select {
    width: 90%;
    padding: 12px;
    margin: 10px 0;
    border-radius: 8px;
    border: 1px solid #999;
    font-size: 16px;
}

.contact-box button {
    padding: 12px 30px;
    border: none;
    background: #2d6a4f;
    color: white;
    font-size: 16px;
    border-radius: 8px;
    cursor: pointer;
}

/* Floating Buttons */
.float-btn {
    position: fixed;
    bottom: 20px;
    right: 20px;
    display: flex;
    flex-direction: column;
    gap: 12px;
    z-index: 999;
}

.float-btn a {
    background: #25D366;
    color: white;
    padding: 14px 18px;
    border-radius: 50%;
    font-size: 22px;
    text-decoration: none;
    text-align: center;
    box-shadow: 0 3px 5px rgba(0,0,0,0.3);
}

.call-btn {
    background: #0077ff !important;
}

/* Responsive */
@media(max-width: 768px){
    .products {
        flex-direction: column;
        align-items: center;
    }
}
</style>
</head>

<body>

<header>Resonance Agro Farm</header>

<div class="hero">Fresh Dairy Products Daily</div>

<div class="section">
    <h2>Our Fresh Products</h2>
    <div class="products">
        <div class="product-card">
            <img src="https://images.unsplash.com/photo-1582719478250-c89cae4dc85b?auto=format&fit=crop&w=800&q=60" alt="Milk">
            <h3>Fresh Milk</h3>
            <p>Pure and hygienic cow milk delivered daily.</p>
        </div>

        <div class="product-card">
            <img src="https://images.unsplash.com/photo-1601050690597-df5f18f02812?auto=format&fit=crop&w=800&q=60" alt="Yoghurt">
            <h3>Yoghurt (Dahi)</h3>
            <p>Thick, rich, traditional Nepali yoghurt.</p>
        </div>

        <div class="product-card">
            <img src="https://images.unsplash.com/photo-1623238919015-208c3f8bc5a0?auto=format&fit=crop&w=800&q=60" alt="Paneer">
            <h3>Paneer</h3>
            <p>Fresh and soft paneer made from pure cow milk.</p>
        </div>
    </div>
</div>

<div class="section">
    <h2>Order / Contact Us</h2>

    <div class="contact-box">
        <h3>Send Your Order Request</h3>

        <input type="text" id="name" placeholder="Your Name" required>
        <input type="text" id="phone" placeholder="Your Phone Number" required>
        <textarea id="order" rows="4" placeholder="Your Order (example: 2L Milk, 1kg Paneer)" required></textarea>
        
        <select id="whatsappNumber">
            <option value="9779841777776">9841777776</option>
            <option value="9779842871707">9842971707</option>
            <option value="9779851057480">9851057480</option>
        </select>

        <button onclick="sendWhatsApp()">Send via WhatsApp</button>
        <p style="margin-top:10px;">Or call us: 9841777776 | 9842871707 | 9851057480</p>
        <p>Email: <a href="mailto:pbbp922@gmail.com">pbbp922@gmail.com</a></p>
    </div>
</div>

<!-- Floating Buttons -->
<div class="float-btn">
    <a href="#" onclick="sendWhatsApp()">💬</a>
    <a href="tel:9841777776" class="call-btn">📞</a>
</div>

<script>
function sendWhatsApp() {
    let name = document.getElementById('name').value.trim();
    let phone = document.getElementById('phone').value.trim();
    let order = document.getElementById('order').value.trim();
    let number = document.getElementById('whatsappNumber').value;

    if(!name || !phone || !order){
        alert("Please fill all fields before sending.");
        return;
    }

    let msg = `Hello! I am ${name} (${phone}). I want to order: ${order}`;
    let url = `https://api.whatsapp.com/send?phone=${number}&text=${encodeURIComponent(msg)}`;
    window.open(url, '_blank');
}
</script>

</body>
</html>
