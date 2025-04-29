<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sarker Cookeris - Kitchen Appliances</title>
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      background-color: #e9f2fb;
      color: #333;
    }
    header {
      background-color: #0056b3;
      color: white;
      padding: 1rem;
      text-align: center;
    }
    nav ul {
      list-style: none;
      display: flex;
      justify-content: center;
      background-color: #007bff;
      margin: 0;
      padding: 0.5rem;
    }
    nav ul li {
      margin: 0 15px;
    }
    nav ul li a {
      color: white;
      text-decoration: none;
      font-weight: bold;
    }
    section {
      padding: 2rem;
      max-width: 1000px;
      margin: auto;
    }
    .product-gallery {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
      gap: 1.5rem;
    }
    .product {
      background: white;
      padding: 1rem;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      text-align: center;
      transition: transform 0.3s;
    }
    .product:hover {
      transform: scale(1.02);
    }
    .product img {
      max-width: 100%;
      height: auto;
      border-radius: 8px;
    }
    form input, form textarea, form select, form button {
      display: block;
      width: 100%;
      margin-bottom: 1rem;
      padding: 0.75rem;
      border: 1px solid #ccc;
      border-radius: 6px;
      font-size: 1rem;
    }
    form button {
      background-color: #007bff;
      color: white;
      border: none;
      cursor: pointer;
    }
    form button:hover {
      background-color: #0056b3;
    }
    footer {
      background-color: #0056b3;
      color: white;
      text-align: center;
      padding: 1rem;
      margin-top: 2rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>Sarker Cookeris</h1>
    <nav>
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#shop">Shop</a></li>
        <li><a href="#order">Order</a></li>
        <li><a href="#cart">Cart</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>  <section id="home">
    <h2>Welcome to Sarker Cookeris</h2>
    <p>Your one-stop shop for quality kitchen appliances.</p>
  </section>  <section id="about">
    <h2>About Us</h2>
    <p>We provide top-tier kitchen appliances to meet all your cooking needs.</p>
  </section>  <section id="services">
    <h2>Services</h2>
    <ul>
      <li>Home Delivery</li>
      <li>Product Installation</li>
      <li>Customer Support</li>
    </ul>
  </section>  <section id="shop">
    <h2>Shop</h2>
    <div class="product-gallery">
      <div class="product">
        <img src="product1.jpg" alt="Cooker X1">
        <h3>Cooker X1</h3>
        <p>$120.00</p>
        <button onclick="addToCart('Cooker X1', 120)">Add to Cart</button>
      </div>
    </div>
  </section>  <section id="order">
    <h2>Place an Order</h2>
    <form id="order-form" onsubmit="processOrder(event)">
      <input type="text" id="name" placeholder="Full Name" required>
      <input type="email" id="email" placeholder="Email" required>
      <input type="text" id="product" placeholder="Product Name" required>
      <input type="number" id="quantity" placeholder="Quantity" required>
      <select id="payment-method" required>
        <option value="">Select Payment Method</option>
        <option value="card">Online Payment (Card)</option>
        <option value="cod">Cash on Delivery</option>
      </select>
      <button type="submit">Submit Order</button>
    </form>
  </section>  <section id="cart">
    <h2>Your Cart</h2>
    <div id="cart-content">
      <p>No items in cart.</p>
    </div>
  </section>  <section id="contact">
    <h2>Contact Us</h2>
    <form>
      <input type="text" placeholder="Name" required>
      <input type="email" placeholder="Email" required>
      <textarea placeholder="Your Message" required></textarea>
      <button type="submit">Send</button>
    </form>
  </section>  <footer>
    <p>&copy; 2025 Sarker Cookeris. All rights reserved.</p>
  </footer>  <script>
    let cart = [];

    function addToCart(name, price) {
      cart.push({ name, price });
      updateCart();
    }

    function updateCart() {
      const cartContent = document.getElementById('cart-content');
      if (cart.length === 0) {
        cartContent.innerHTML = '<p>No items in cart.</p>';
      } else {
        cartContent.innerHTML = cart.map(item => `<p>${item.name} - $${item.price}</p>`).join('');
      }
    }

    function processOrder(event) {
      event.preventDefault();
      const method = document.getElementById('payment-method').value;
      if (method === 'card') {
        alert('Redirecting to secure online payment portal...');
        // Here you'd redirect to Stripe, PayPal, etc.
      } else {
        alert('Order placed with Cash on Delivery. We will contact you soon.');
      }
      document.getElementById('order-form').reset();
      cart = [];
      updateCart();
    }
  </script></body>
</html>
