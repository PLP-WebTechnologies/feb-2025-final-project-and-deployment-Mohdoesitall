<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>E-commerce Website</title>
  <style>
    /* General Styles */
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
    }

    header {
      background-color: #333;
      color: white;
      padding: 20px;
    }

    header h1 {
      margin: 0;
    }

    nav ul {
      list-style-type: none;
      padding: 0;
    }

    nav ul li {
      display: inline;
      margin-right: 20px;
    }

    nav a {
      color: white;
      text-decoration: none;
    }

    #featured {
      display: flex;
      justify-content: space-around;
      margin: 20px 0;
    }

    .product-card {
      border: 1px solid #ccc;
      padding: 20px;
      text-align: center;
      background-color: white;
    }

    .product-card img {
      width: 150px;
      height: 150px;
      object-fit: cover;
    }

    button {
      background-color: #007bff;
      color: white;
      border: none;
      padding: 10px 20px;
      cursor: pointer;
    }

    button:hover {
      background-color: #0056b3;
    }

    footer {
      text-align: center;
      padding: 20px;
      background-color: #333;
      color: white;
    }
  </style>
</head>
<body>
  <header>
    <h1>My E-commerce Store</h1>
    <nav>
      <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="shop.html">Shop</a></li>
        <li><a href="cart.html">Cart</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <section id="featured">
      <h2>Featured Products</h2>
      <div class="product-card">
        <img src="https://via.placeholder.com/150" alt="Product 1">
        <h3>Product 1</h3>
        <p>$19.99</p>
        <button class="add-to-cart" data-product="Product 1" data-price="19.99">Add to Cart</button>
      </div>
      <div class="product-card">
        <img src="https://via.placeholder.com/150" alt="Product 2">
        <h3>Product 2</h3>
        <p>$29.99</p>
        <button class="add-to-cart" data-product="Product 2" data-price="29.99">Add to Cart</button>
      </div>
    </section>
  </main>

  <footer>
    <p>&copy; 2025 My E-commerce Store</p>
  </footer>

  <script>
    // Cart functionality
    let cart = JSON.parse(localStorage.getItem('cart')) || [];

    document.querySelectorAll('.add-to-cart').forEach(button => {
      button.addEventListener('click', (event) => {
        const productName = event.target.getAttribute('data-product');
        const productPrice = parseFloat(event.target.getAttribute('data-price'));

        cart.push({ name: productName, price: productPrice });
        localStorage.setItem('cart', JSON.stringify(cart));

        alert(`${productName} has been added to your cart!`);
      });
    });
  </script>
</body>
</html>
