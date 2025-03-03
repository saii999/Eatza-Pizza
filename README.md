<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Eatza Pizza</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        :root {
            --primary-color: #FF4444;
            --secondary-color: #FFF9E6;
            --accent-color: #FFD700;
        }
        
        .product-card {
            transition: transform 0.3s;
            background: var(--secondary-color);
            border: 1px solid rgba(255, 68, 68, 0.1);
            margin-bottom: 1.5rem;
        }
        
        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(255, 68, 68, 0.1);
        }
        
        .hero-gradient {
            background: linear-gradient(135deg, var(--primary-color) 0%, #0556d9 100%);
            padding: 4rem 0;
            position: relative;
            color: white;
        }

        .hero-gradient::before {
            content: "";
            background: url('https://images.unsplash.com/photo-1600891964599-f61ba0e24092') no-repeat center center/cover;
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0.5;
            z-index: 0;
        }

        .hero-content {
            position: relative;
            z-index: 1;
        }
        
        .cart-badge {
            top: -8px;
            right: -8px;
        }
        
        footer {
            background: #2C2C2C;
            color: white;
            padding: 1.5rem 0;
            margin-top: 3rem;
        }
        
        .modal-header {
            background: var(--primary-color);
            color: white;
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar navbar-expand-lg navbar-light bg-white shadow-sm fixed-top">
        <div class="container">
            <a class="navbar-brand fw-bold" href="#" style="color: var(--primary-color)">🍕 EATZA PIZZA</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item">
                        <a class="nav-link active" href="#">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Shop</a>
                    </li>
                    <li class="nav-item position-relative">
                        <button class="btn btn-link nav-link" data-bs-toggle="modal" data-bs-target="#cartModal">
                            🛒 Cart
                            <span class="position-absolute cart-badge badge bg-danger">0</span>
                        </button>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <header class="hero-gradient text-white">
        <div class="container text-center hero-content">
            <h1 class="display-4 mb-4">Delicious Pizzas Await</h1>
            <p class="lead">Discover our mouth-watering pizzas delivered fresh daily</p>
            <button class="btn btn-light btn-lg mt-3">Order Now</button>
        </div>
    </header>

    <!-- Products Grid -->
    <main class="container" style="padding-top: 7rem; padding-bottom: 4rem;">
        <h2 class="mb-4 text-center">Our Pizza Collection</h2>
        <div class="row g-4" id="products">
            <!-- Dynamic content -->
        </div>
    </main>

    <!-- Customer Reviews -->
    <section class="container my-5">
        <h2 class="mb-4 text-center">Customer Reviews</h2>
        <div class="row">
            <div class="col-md-4">
                <div class="card">
                    <div class="card-body">
                        <h5 class="card-title">Arun Kumar</h5>
                        <p class="card-text">"The best pizza I've ever had! Highly recommend the spicy pepperoni."</p>
                    </div>
                </div>
            </div>
            <div class="col-md-4">
                <div class="card">
                    <div class="card-body">
                        <h5 class="card-title">Jane Smith</h5>
                        <p class="card-text">"Amazing flavors and super fresh ingredients. Will order again!"</p>
                    </div>
                </div>
            </div>
            <div class="col-md-4">
                <div class="card">
                    <div class="card-body">
                        <h5 class="card-title">Sam Wilson</h5>
                        <p class="card-text">"Fast delivery and the pizza was still hot. Great service!"</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container text-center">
            <p class="mb-0">
                © 2025 All rights reserved and designed by <a href="#" style="color: var(--accent-color)">N.Saiiprasanna</a>
                <br>
                <span class="d-block text-muted mt-1" style="font-size: 0.8em">
                    Crafted with ❤️ for pizza lovers worldwide
                </span>
            </p>
        </div>
    </footer>

    <!-- Cart Modal -->
    <div class="modal fade" id="cartModal">
        <div class="modal-dialog modal-lg">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title">Your Shopping Cart</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
                </div>
                <div class="modal-body">
                    <ul class="list-group mb-3" id="cartItems">
                        <!-- Dynamic content -->
                    </ul>
                    <div class="d-flex justify-content-between align-items-center">
                        <h5>Total: ₹<span id="cartTotal">0.00</span></h5>
                        <button class="btn btn-primary">Secure Checkout</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Scripts -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        // Updated product data with working images
        const products = [
            { 
                id: 1, 
                name: "🍕 Margherita Pizza", 
                price: 199,
                image: "https://cookieandkate.com/images/2021/07/classic-margherita-pizza-1021x1536.jpg" 
            },
            { 
                id: 2, 
                name: "🍕 Pepperoni Pizza", 
                price: 299,
                image: "https://www.iheartnaptime.net/wp-content/uploads/2023/04/Pepperoni-Pizza-Recipe-I-Heart-Naptime.jpg" 
            },
            { 
                id: 3, 
                name: "🍕 BBQ Chicken Pizza", 
                price: 349,
                image: "https://s23209.pcdn.co/wp-content/uploads/2021/10/BBQ-Chicken-PizzaIMG_0027-1024x1536.jpg" 
            },
            { 
                id: 4, 
                name: "🍕 Veggie Pizza", 
                price: 249,
                image: "https://th.bing.com/th/id/OIP.Xx0j4C97GRtmrBzJHq8RFgHaLG?rs=1&pid=ImgDetMain" 
            }
        ];

        // Cart System
        let cart = JSON.parse(localStorage.getItem('pizzaCart')) || [];
        
        function renderProducts() {
            const container = document.getElementById('products');
            container.innerHTML = products.map(product => `
                <div class="col-md-6 col-lg-4 col-xl-3">
                    <div class="card product-card h-100">
                        <img src="${product.image}" class="card-img-top p-3" alt="${product.name}">
                        <div class="card-body d-flex flex-column">
                            <h5 class="card-title">${product.name}</h5>
                            <p class="card-text mt-auto">₹${product.price.toFixed(2)}</p>
                            <button onclick="addToCart(${product.id})" 
                                class="btn btn-warning w-100 mt-2">
                                Add to Cart
                            </button>
                        </div>
                    </div>
                </div>
            `).join('');
        }

        function updateCartUI() {
            document.querySelector('.cart-badge').textContent = cart.length;
            localStorage.setItem('pizzaCart', JSON.stringify(cart));
        }

        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            cart.push(product);
            updateCartUI();
            renderCartItems();
            new bootstrap.Toast(document.createElement('div'), {
                body: `${product.name} added to cart!`,
                className: 'bg-success text-white',
                delay: 2000
            }).show();
        }

        function renderCartItems() {
            const cartItems = document.getElementById('cartItems');
            const total = cart.reduce((sum, item) => sum + item.price, 0);
            
            cartItems.innerHTML = cart.map((item, index) => `
                <li class="list-group-item d-flex justify-content-between align-items-center">
                    <div>
                        <span class="fw-bold">${item.name}</span>
                        <br>
                        <small class="text-muted">₹${item.price.toFixed(2)}</small>
                    </div>
                    <button onclick="removeItem(${index})" class="btn btn-sm btn-danger">
                        ×
                    </button>
                </li>
            `).join('');
            
            document.getElementById('cartTotal').textContent = total.toFixed(2);
        }

        function removeItem(index) {
            cart.splice(index, 1);
            updateCartUI();
            renderCartItems();
        }

        // Initialization
        document.addEventListener('DOMContentLoaded', () => {
            renderProducts();
            renderCartItems();
        });
    </script>
</body>
</html>
