<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>MakeUp Store</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: Arial, sans-serif; }
    body {
      background: url('https://images.unsplash.com/photo-1522337660859-02fbefca4702') no-repeat center center fixed;
      background-size: cover;
      color: #333;
    }
    header { background: rgba(240, 140, 164, 0.9); padding: 1rem; text-align: center; }
    header h1 { color: white; }

    nav { display: flex; justify-content: center; background: rgba(255, 214, 224, 0.9); padding: 10px; }
    nav a { margin: 0 15px; text-decoration: none; color: #333; font-weight: bold; }

    .products { display: flex; flex-wrap: wrap; justify-content: center; padding: 2rem; gap: 20px; }
    .product { border: 1px solid #ddd; padding: 15px; border-radius: 10px; width: 250px; text-align: center; background: rgba(255, 240, 246, 0.9); }
    .product img { width: 100%; height: auto; border-radius: 10px; }
    .product h3 { margin: 10px 0; }
    .product p { color: #f08ca4; font-weight: bold; }
    .product button { margin-top: 10px; padding: 10px; background: #f08ca4; border: none; color: white; cursor: pointer; border-radius: 5px; }

    .cart { position: fixed; right: 10px; top: 100px; background: white; border: 1px solid #ccc; padding: 10px; width: 300px; max-height: 400px; overflow-y: auto; border-radius: 10px; display: none; }
    .cart h2 { font-size: 18px; margin-bottom: 10px; }
    .cart-item { margin-bottom: 10px; }
    .checkout-btn { margin-top: 10px; padding: 10px; background: #28a745; color: white; border: none; cursor: pointer; border-radius: 5px; width: 100%; }

    .shipping-form {
      margin-top: 10px;
      display: none;
    }
    .shipping-form input, .shipping-form textarea {
      width: 100%;
      margin-bottom: 10px;
      padding: 8px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    footer { text-align: center; padding: 20px; background: rgba(240, 140, 164, 0.9); color: white; margin-top: 30px; }
    @media (max-width: 600px) {
      .products { flex-direction: column; align-items: center; }
    }
  </style>
</head>
<body>
  <header>
    <h1>MakeUp Glam Store</h1>
  </header>
  <nav>
    <a href="#">Home</a>
    <a href="#products">Products</a>
    <a href="#cart" id="view-cart">Cart (<span id="cart-count">0</span>)</a>
  </nav>

  <section class="products" id="products">
    <div class="product">
      <img src="C:\Users\DELL\OneDrive\Desktop\Web\make-up images\lipstick.jpeg-2.jpg" alt="lipstick">
      <h3>Matte Lipstick</h3>
      <p>Rs 2800</p>
      <button class="add-to-cart" data-name="Matte Lipstick" data-price="2800">Add to Cart</button>
    </div>
    <div class="product">
      <img src="C:\Users\DELL\OneDrive\Desktop\Web\make-up images\Foundation.jpg" alt="Foundation">
      <h3>Silky Foundation</h3>
      <p> Rs 5000</p>
      <button class="add-to-cart" data-name="Silky Foundation" data-price="5000">Add to Cart</button>
    </div>
    <div class="product">
      <img src="C:\Users\DELL\OneDrive\Desktop\Web\make-up images\eyeliner.jpg" alt="Eyeliner">
      <h3>Black Eyeliner</h3>
      <p>Rs 1500</p>
      <button class="add-to-cart" data-name="Black Eyeliner" data-price="1500">Add to Cart</button>
    </div>
    <div class="product">
      <img src="C:\Users\DELL\OneDrive\Desktop\Web\make-up images\eyeshadow.jpg" alt="Eyeshadow">
      <h3>Eyeshadow pallete</h3>
      <p>Rs 3OOO</p>
      <button class="add-to-cart" data-name="Black Eyeliner" data-price="3000">Add to Cart</button>
    </div>
     <div class="product">
      <img src="C:\Users\DELL\OneDrive\Desktop\Web\make-up images\blush.jpg" alt="Blush">
      <h3>Peach Blush</h3>
      <p>Rs 2500</p>
      <button class="add-to-cart" data-name="Peach Blush" data-price="2500">Add to Cart</button>
    </div>
     <div class="product">
      <img src="C:\Users\DELL\OneDrive\Desktop\Web\make-up images\mascara.jpg" alt="Mascara">
      <h3>Lenghty Lashes mascara</h3>
      <p>Rs 2000</p>
      <button class="add-to-cart" data-name="Lenghty lashes mascara" data-price="2000">Add to Cart</button>
    </div>
    <div class="product">
      <img src="C:\Users\DELL\OneDrive\Desktop\Web\make-up images\highlighter.jpg" alt="Highlighter">
      <h3>Glowy Highlighter</h3>
      <p>Rs 4500</p>
      <button class="add-to-cart" data-name="Glowy Highlighter" data-price="2000">Add to Cart</button>
    </div>
    <div class="product">
      <img src="C:\Users\DELL\OneDrive\Desktop\Web\make-up images\brow.jpg" alt="Browkit">
      <h3>For Dark & Bold Brow</h3>
      <p>Rs 2000</p>
      <button class="add-to-cart" data-name="Dark & Brow" data-price="2000">Add to Cart</button>
    </div>
    <div class="product">
      <img src="C:\Users\DELL\OneDrive\Desktop\Web\make-up images\lip blam.jpg" alt="Lipblam">
      <h3>Glossy Lipblam stick</h3>
      <p>Rs 3200</p>
      <button class="add-to-cart" data-name="Glossy Lipblam stick" data-price="2000">Add to Cart</button>
    </div>
    <div class="product">
      <img src="C:\Users\DELL\OneDrive\Desktop\Web\make-up images\concelar.webp" alt="Concelar">
      <h3>Concelar & color corrector pallete</h3>
      <p>Rs 3500</p>
      <button class="add-to-cart" data-name="Concelar & color corrector pallete" data-price="3500">Add to Cart</button>
    </div>
  </section>

  <div class="cart" id="cart-box">
    <h2>Your Cart</h2>
    <div id="cart-items"></div>
    <button class="checkout-btn" id="checkout">Proceed to Payment</button>
    <form class="shipping-form" id="shipping-form">
      <h3>Shipping Details</h3>
      <input type="text" id="fullname" placeholder="Full Name" required>
      <input type="text" id="address" placeholder="Shipping Address" required>
      <input type="text" id="city" placeholder="City" required>
      <input type="text" id="zipcode" placeholder="Zip Code" required>
      <input type="text" id="country" placeholder="Country" required>
      <textarea id="note" placeholder="Additional Notes (Optional)"></textarea>
      <button type="submit" class="checkout-btn" style="background:#007bff">Pay Now</button>
    </form>
  </div>
  <footer>
    <p>&copy; 2025 MakeUp Glam Store. All rights reserved.</p>
  </footer>

  <script>
    let cart = [];

    function updateCartDisplay() {
      const cartItems = $("#cart-items");
      cartItems.html("");
      cart.forEach((item, index) => {
        cartItems.append(`<div class="cart-item">${item.name} - Rs${item.price}</div>`);
      });
      $("#cart-count").text(cart.length);
    }

    $(".add-to-cart").click(function () {
      const name = $(this).data("name");
      const price = $(this).data("price");
      cart.push({ name, price });
      updateCartDisplay();
      alert(name + " added to cart.");
    });

    $("#view-cart").click(function (e) {
      e.preventDefault();
      $("#cart-box").toggle();
    });

    $("#checkout").click(function () {
      if (cart.length === 0) {
        alert("Your cart is empty!");
        return;
      }
      $("#shipping-form").slideDown();
    });

    $("#shipping-form").submit(function (e) {
      e.preventDefault();
      const name = $("#fullname").val();
      const total = cart.reduce((sum, item) => sum + parseFloat(item.price), 0);
      alert(`Thank you, ${name}! Your order of $${total.toFixed(2)} has been placed.\nShipping soon.`);
      cart = [];
      updateCartDisplay();
      $("#shipping-form").slideUp();
      $("#cart-box").hide();
    });
  </script>
</body>
</html>
