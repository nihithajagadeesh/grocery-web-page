<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fresh Grocery Store</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            background-color: #f7f9fc;
            color: #333;
        }

        /* Header Styles */
        .header {
            background: linear-gradient(135deg, #43c6ac 0%, #191654 100%);
            padding: 1.5rem;
            color: white;
            box-shadow: 0 2px 15px rgba(0,0,0,0.1);
        }

        .header-top {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 20px;
        }

        .store-name {
            font-size: 2rem;
            font-weight: bold;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }

        .search-form {
            flex: 1;
            max-width: 500px;
            margin: 0 2rem;
            position: relative;
        }

        .search-form input[type="text"] {
            width: 100%;
            padding: 0.8rem 1rem;
            border: none;
            border-radius: 25px;
            font-size: 1rem;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        .search-form button {
            position: absolute;
            right: 10px;
            top: 50%;
            transform: translateY(-50%);
            background: #43c6ac;
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            color: white;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .search-form button:hover {
            background: #191654;
        }

        .cart-icon {
            background: white;
            color: #191654;
            padding: 10px 20px;
            border-radius: 25px;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: transform 0.3s ease;
        }

        .cart-icon:hover {
            transform: translateY(-2px);
        }

        /* Navigation Styles */
        .nav {
            background: white;
            padding: 1rem;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .nav ul {
            list-style: none;
            display: flex;
            gap: 2rem;
            justify-content: space-between;
            flex-wrap: wrap;
        }

        .nav a {
            color: #333;
            text-decoration: none;
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            transition: all 0.3s ease;
        }

        .nav a:hover {
            background: #43c6ac;
            color: white;
        }

        /* Main Content Styles */
        .main {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 20px;
        }

        .banner {
            background: linear-gradient(45deg, #ff6b6b, #ffd93d);
            color: white;
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            margin-bottom: 3rem;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        .banner h2 {
            font-size: 2rem;
            margin-bottom: 1rem;
        }

        .banner p {
            font-size: 1.2rem;
        }

        .category-title {
            font-size: 1.8rem;
            color: #191654;
            margin: 2rem 0;
            padding-bottom: 0.5rem;
            border-bottom: 3px solid #43c6ac;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .product-card {
            background: white;
            border-radius: 15px;
            padding: 1.5rem;
            text-align: center;
            transition: transform 0.3s ease;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        }

        .product-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 10px;
            margin-bottom: 1rem;
        }

        .product-title {
            font-size: 1.2rem;
            color: #191654;
            margin: 1rem 0;
        }

        .product-price {
            font-size: 1.4rem;
            color: #43c6ac;
            font-weight: bold;
            margin: 0.5rem 0;
        }

        .product-unit {
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .add-to-cart-btn {
            background: #43c6ac;
            color: white;
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 100%;
            font-size: 1rem;
        }

        .add-to-cart-btn:hover {
            background: #191654;
        }

        /* Footer Styles */
        .footer {
            background: #191654;
            color: white;
            padding: 4rem 0 2rem;
            margin-top: 4rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
        }

        .footer-section h3 {
            color: #43c6ac;
            margin-bottom: 1.5rem;
            font-size: 1.3rem;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 0.8rem;
        }

        .footer-section a {
            color: #fff;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-section a:hover {
            color: #43c6ac;
        }

        .footer-bottom {
            text-align: center;
            margin-top: 3rem;
            padding-top: 2rem;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .header-top {
                flex-direction: column;
                gap: 1rem;
            }

            .search-form {
                width: 100%;
                margin: 1rem 0;
            }

            .nav ul {
                flex-direction: column;
                text-align: center;
            }

            .nav li {
                width: 100%;
            }

            .products-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
        }

        /* Special Offers Badge */
        .special-offer-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background: #ff6b6b;
            color: white;
            padding: 5px 10px;
            border-radius: 15px;
            font-size: 0.9rem;
        }

        /* Stock Status */
        .stock-status {
            color: #28a745;
            font-size: 0.9rem;
            margin: 0.5rem 0;
        }

        .out-of-stock {
            color: #dc3545;
        }
    </style>
</head>
<body>
    <header class="header">
        <div class="header-top">
            <h1 class="store-name">Fresh Grocery</h1>
            <form class="search-form">
                <input type="text" placeholder="Search for products...">
                <button type="submit">Search</button>
            </form>
            <a href="#" class="cart-icon">
                🛒 Cart (0)
            </a>
        </div>
    </header>

    <nav class="nav">
        <div class="nav-container">
            <ul>
                <li><a href="#fruits">Fruits & Vegetables</a></li>
                <li><a href="#dairy">Dairy & Eggs</a></li>
                <li><a href="#bakery">Bakery</a></li>
                <li><a href="#beverages">Beverages</a></li>
                <li><a href="#pantry">Pantry</a></li>
                <li><a href="#household">Household</a></li>
            </ul>
        </div>
    </nav>

    <main class="main">
        <section class="banner">
            <h2>🌟 Weekend Special Offers!</h2>
            <p>Get 20% off on fresh vegetables and fruits</p>
        </section>

        <section id="fruits">
            <h2 class="category-title">Fresh Fruits & Vegetables</h2>
            <div class="products-grid">
                <div class="product-card">
                    <img src="/api/placeholder/250/200" alt="Fresh Apples" class="product-image">
                    <div class="special-offer-badge">20% OFF</div>
                    <h3 class="product-title">Fresh Organic Apples</h3>
                    <p class="product-price">$2.99</p>
                    <p class="product-unit">per pound</p>
                    <p class="stock-status">In Stock</p>
                    <button class="add-to-cart-btn">Add to Cart</button>
                </div>
                
                <div class="product-card">
                    <img src="/api/placeholder/250/200" alt="Bananas" class="product-image">
                    <h3 class="product-title">Ripe Bananas</h3>
                    <p class="product-price">$1.99</p>
                    <p class="product-unit">per bunch</p>
                    <p class="stock-status">In Stock</p>
                    <button class="add-to-cart-btn">Add to Cart</button>
                </div>

                <div class="product-card">
                    <img src="/api/placeholder/250/200" alt="Carrots" class="product-image">
                    <h3 class="product-title">Fresh Carrots</h3>
                    <p class="product-price">$1.49</p>
                    <p class="product-unit">per pound</p>
                    <p class="stock-status">In Stock</p>
                    <button class="add-to-cart-btn">Add to Cart</button>
                </div>
            </div>
        </section>

        <section id="dairy">
            <h2 class="category-title">Dairy & Eggs</h2>
            <div class="products-grid">
                <div class="product-card">
                    <img src="/api/placeholder/250/200" alt="Milk" class="product-image">
                    <h3 class="product-title">Organic Whole Milk</h3>
                    <p class="product-price">$4.99</p>
                    <p class="product-unit">1 gallon</p>
                    <p class="stock-status">In Stock</p>
                    <button class="add-to-cart-btn">Add to Cart</button>
                </div>

                <div class="product-card">
                    <img src="/api/placeholder/250/200" alt="Eggs" class="product-image">
                    <div class="special-offer-badge">New</div>
                    <h3 class="product-title">Free-Range Eggs</h3>
                    <p class="product-price">$5.99</p>
                    <p class="product-unit">dozen</p>
                    <p class="stock-status">In Stock</p>
                    <button class="add-to-cart-btn">Add to Cart</button>
                </div>

                <div class="product-card">
                    <img src="/api/placeholder/250/200" alt="Cheese" class="product-image">
                    <h3 class="product-title">Aged Cheddar</h3>
                    <p class="product-price">$6.99</p>
                    <p class="product-unit">per pound</p>
                    <p class="stock-status out-of-stock">Out of Stock</p>
                    <button class="add-to-cart-btn" disabled>Out of Stock</button>
                </div>
            </div>
        </section>

        <section id="beverages">
            <h2 class="category-title">Beverages</h2>
            <div class="products-grid">
                <div class="product-card">
                    <img src="/api/placeholder/250/200" alt="Coffee" class="product-image">
                    <h3 class="product-title">Premium Coffee</h3>
                    <p class="product-price">$12.99</p>
                    <p class="product-unit">1 pound</p>
                    <p class="stock-status">In Stock</p>
                    <button class="add-to-cart-btn">Add to Cart</button>
                </div>

                <div class="product-card">
                    <img src="/api/placeholder/250/200" alt="Tea" class="product-image">
                    <h3 class="product-title">Green Tea</h3>
                    <p class="product-price">$4.99</p>
                    <p class="product-unit">20 bags</p>
                    <p class="stock-status">In Stock</p>
                    <button class="add-to-cart-btn">Add to Cart
                </ul>
            </div>
        </div>
    </footer>
</body>
</html>
