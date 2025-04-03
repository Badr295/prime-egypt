# prime-egypt
selling prime in egypt
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prime Hydration | Official Egypt Store</title>
    <style>
        /* Global Styles */
        :root {
            --prime-blue: #0066cc;
            --prime-red: #ff0000;
            --prime-purple: #6600cc;
            --prime-black: #111111;
            --prime-white: #ffffff;
            --sold-out: #999999;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            background-color: #f5f5f5;
            color: var(--prime-black);
        }
        
        /* Header Styles */
        header {
            background-color: var(--prime-black);
            color: var(--prime-white);
            padding: 1rem 2rem;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--prime-white);
            text-decoration: none;
        }
        
        .logo span {
            color: var(--prime-blue);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 2rem;
        }
        
        nav ul li a {
            color: var(--prime-white);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        nav ul li a:hover {
            color: var(--prime-blue);
        }
        
        .cart-icon {
            position: relative;
            margin-left: 2rem;
        }
        
        .cart-count {
            position: absolute;
            top: -10px;
            right: -10px;
            background-color: var(--prime-red);
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.7rem;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('https://images.unsplash.com/photo-1551029506-0807df4e2031?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80');
            background-size: cover;
            background-position: center;
            height: 80vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--prime-white);
        }
        
        .hero-content {
            max-width: 800px;
            padding: 2rem;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
        }
        
        .btn {
            display: inline-block;
            background-color: var(--prime-blue);
            color: var(--prime-white);
            padding: 0.8rem 2rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: background-color 0.3s, transform 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background-color: var(--prime-purple);
            transform: translateY(-3px);
        }
        
        .btn-sold-out {
            background-color: var(--sold-out);
            cursor: not-allowed;
        }
        
        /* Products Section */
        .products {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            font-size: 2.5rem;
            color: var(--prime-black);
        }
        
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
        }
        
        .product-card {
            background-color: var(--prime-white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            position: relative;
        }
        
        .product-card.sold-out::after {
            content: "SOLD OUT";
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: var(--prime-red);
            color: white;
            padding: 0.3rem 0.6rem;
            border-radius: 5px;
            font-weight: bold;
            font-size: 0.8rem;
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
        }
        
        .product-image {
            height: 250px;
            background-size: contain;
            background-position: center;
            background-repeat: no-repeat;
            background-color: #f9f9f9;
        }
        
        .product-info {
            padding: 1.5rem;
        }
        
        .product-title {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
        }
        
        .product-price {
            font-size: 1.2rem;
            font-weight: bold;
            color: var(--prime-blue);
            margin-bottom: 1rem;
        }
        
        /* Cart Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.7);
            z-index: 1000;
            overflow-y: auto;
        }
        
        .modal-content {
            background-color: white;
            margin: 5% auto;
            padding: 2rem;
            width: 80%;
            max-width: 800px;
            border-radius: 10px;
            position: relative;
        }
        
        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        .cart-items {
            margin: 2rem 0;
        }
        
        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
            border-bottom: 1px solid #eee;
        }
        
        .cart-item img {
            width: 80px;
            height: 80px;
            object-fit: contain;
        }
        
        .cart-item-info {
            flex-grow: 1;
            padding: 0 1rem;
        }
        
        .cart-item-price {
            font-weight: bold;
        }
        
        .cart-total {
            text-align: right;
            font-size: 1.3rem;
            margin: 1rem 0;
            font-weight: bold;
        }
        
        /* About Section */
        .about {
            background-color: var(--prime-black);
            color: var(--prime-white);
            padding: 5rem 2rem;
            text-align: center;
        }
        
        .about-content {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .about h2 {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            color: var(--prime-white);
        }
        
        .about p {
            font-size: 1.1rem;
            line-height: 1.6;
            margin-bottom: 2rem;
        }
        
        /* Contact Section */
        .contact {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background-color: var(--prime-white);
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
        }
        
        .form-group textarea {
            height: 150px;
        }
        
        /* Footer */
        footer {
            background-color: var(--prime-black);
            color: var(--prime-white);
            padding: 3rem 2rem;
            text-align: center;
        }
        
        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .social-links {
            margin: 1.5rem 0;
        }
        
        .social-links a {
            color: var(--prime-white);
            margin: 0 1rem;
            font-size: 1.5rem;
            transition: color 0.3s;
        }
        
        .social-links a:hover {
            color: var(--prime-blue);
        }
        
        .copyright {
            margin-top: 1.5rem;
            font-size: 0.9rem;
            color: #aaa;
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul {
                margin-top: 1rem;
                justify-content: center;
            }
            
            nav ul li {
                margin: 0 1rem;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
            
            .modal-content {
                width: 95%;
                margin: 2% auto;
                padding: 1rem;
            }
            
            .cart-item {
                flex-direction: column;
                text-align: center;
            }
            
            .cart-item img {
                margin-bottom: 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-container">
            <a href="#" class="logo">PRIME<span>.</span>EG</a>
            <nav>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#products">Products</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#contact">Contact</a></li>
                    <li class="cart-icon">
                        <a href="#" id="cartButton">
                            <i class="fas fa-shopping-cart"></i>
                            <span class="cart-count" id="cartCount">0</span>
                        </a>
                    </li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Hydrate Better with PRIME</h1>
            <p>The ultimate hydration drink, now available in Egypt. Fuel your body with the perfect balance of electrolytes and vitamins.</p>
            <a href="#products" class="btn">Shop Now</a>
        </div>
    </section>

    <!-- Products Section -->
    <section class="products" id="products">
        <h2 class="section-title">Our Products</h2>
        <div class="product-grid">
            <!-- Product 1 - Blue Raspberry -->
            <div class="product-card">
                <div class="product-image" style="background-image: url('https://i5.walmartimages.com/asr/5a9e5b0e-7d6a-4c7e-9c3b-5e5f5b5e5e5e.1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a');"></div>
                <div class="product-info">
                    <h3 class="product-title">PRIME Hydration - Blue Raspberry</h3>
                    <p class="product-price">EGP 200.00</p>
                    <button class="btn add-to-cart" data-id="1" data-name="Blue Raspberry" data-price="200" data-image="https://i5.walmartimages.com/asr/5a9e5b0e-7d6a-4c7e-9c3b-5e5f5b5e5e5e.1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a">Add to Cart</button>
                </div>
            </div>
            
            <!-- Product 2 - Tropical Punch -->
            <div class="product-card">
                <div class="product-image" style="background-image: url('https://i5.walmartimages.com/asr/5a9e5b0e-7d6a-4c7e-9c3b-5e5f5b5e5e5e.1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a');"></div>
                <div class="product-info">
                    <h3 class="product-title">PRIME Hydration - Tropical Punch</h3>
                    <p class="product-price">EGP 200.00</p>
                    <button class="btn add-to-cart" data-id="2" data-name="Tropical Punch" data-price="200" data-image="https://i5.walmartimages.com/asr/5a9e5b0e-7d6a-4c7e-9c3b-5e5f5b5e5e5e.1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a">Add to Cart</button>
                </div>
            </div>
            
            <!-- Product 3 - Lemon Lime -->
            <div class="product-card">
                <div class="product-image" style="background-image: url('https://i5.walmartimages.com/asr/5a9e5b0e-7d6a-4c7e-9c3b-5e5f5b5e5e5e.1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a');"></div>
                <div class="product-info">
                    <h3 class="product-title">PRIME Hydration - Lemon Lime</h3>
                    <p class="product-price">EGP 200.00</p>
                    <button class="btn add-to-cart" data-id="3" data-name="Lemon Lime" data-price="200" data-image="https://i5.walmartimages.com/asr/5a9e5b0e-7d6a-4c7e-9c3b-5e5f5b5e5e5e.1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a">Add to Cart</button>
                </div>
            </div>
            
            <!-- Product 4 - Ice Pop -->
            <div class="product-card">
                <div class="product-image" style="background-image: url('https://i5.walmartimages.com/asr/5a9e5b0e-7d6a-4c7e-9c3b-5e5f5b5e5e5e.1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a');"></div>
                <div class="product-info">
                    <h3 class="product-title">PRIME Hydration - Ice Pop</h3>
                    <p class="product-price">EGP 200.00</p>
                    <button class="btn add-to-cart" data-id="4" data-name="Ice Pop" data-price="200" data-image="https://i5.walmartimages.com/asr/5a9e5b0e-7d6a-4c7e-9c3b-5e5f5b5e5e5e.1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a">Add to Cart</button>
                </div>
            </div>
            
            <!-- Product 5 - Meta Moon -->
            <div class="product-card">
                <div class="product-image" style="background-image: url('https://i5.walmartimages.com/asr/5a9e5b0e-7d6a-4c7e-9c3b-5e5f5b5e5e5e.1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a');"></div>
                <div class="product-info">
                    <h3 class="product-title">PRIME Hydration - Meta Moon</h3>
                    <p class="product-price">EGP 220.00</p>
                    <button class="btn add-to-cart" data-id="5" data-name="Meta Moon" data-price="220" data-image="https://i5.walmartimages.com/asr/5a9e5b0e-7d6a-4c7e-9c3b-5e5f5b5e5e5e.1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a">Add to Cart</button>
                </div>
            </div>
            
            <!-- Product 6 - Strawberry Watermelon -->
            <div class="product-card">
                <div class="product-image" style="background-image: url('https://i5.walmartimages.com/asr/5a9e5b0e-7d6a-4c7e-9c3b-5e5f5b5e5e5e.1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a');"></div>
                <div class="product-info">
                    <h3 class="product-title">PRIME Hydration - Strawberry Watermelon</h3>
                    <p class="product-price">EGP 220.00</p>
                    <button class="btn add-to-cart" data-id="6" data-name="Strawberry Watermelon" data-price="220" data-image="https://i5.walmartimages.com/asr/5a9e5b0e-7d6a-4c7e-9c3b-5e5f5b5e5e5e.1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a1a">Add to Cart</button>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <div class="about-content">
            <h2>About PRIME Hydration</h2>
            <p>PRIME Hydration was created to fill the void where great taste meets function. With bold, thirst-quenching flavors to help you refresh, replenish, and refuel, PRIME is the perfect boost for any endeavor.</p>
            <p>We're proud to bring PRIME to Egypt, offering athletes and active individuals a superior hydration option with 10% coconut water, BCAAs, antioxidants, and more electrolytes than traditional sports drinks.</p>
            <a href="#contact" class="btn">Contact Us</a>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <h2 class="section-title">Contact Us</h2>
        <div class="contact-form">
            <form id="contactForm">
                <div class="form-group">
                    <label for="name">Name</label>
                    <input type="text" id="name" name="name" required>
                </div>
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="message">Message</label>
                    <textarea id="message" name="message" required></textarea>
                </div>
                <button type="submit" class="btn">Send Message</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <a href="#" class="logo">PRIME<span>.</span>EG</a>
            <div class="social-links">
                <a href="#"><i class="fab fa-facebook"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-tiktok"></i></a>
            </div>
            <p class="copyright">© 2023 PRIME.EG. All Rights Reserved.</p>
        </div>
    </footer>

    <!-- Cart Modal -->
    <div class="modal" id="cartModal">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <h2>Your Cart</h2>
            <div class="cart-items" id="cartItems">
                <!-- Cart items will be added here dynamically -->
                <p>Your cart is empty</p>
            </div>
            <div class="cart-total" id="cartTotal">
                Total: EGP 0.00
            </div>
            <button class="btn" id="checkoutButton">Proceed to Checkout</button>
        </div>
    </div>

    <!-- Font Awesome for icons -->
    <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
    
    <!-- JavaScript -->
    <script>
        // Cart functionality
        let cart = [];
        
        // DOM Elements
        const cartButton = document.getElementById('cartButton');
        const cartModal = document.getElementById('cartModal');
        const closeModal = document.querySelector('.close-modal');
        const cartItemsContainer = document.getElementById('cartItems');
        const cartTotalElement = document.getElementById('cartTotal');
        const cartCountElement = document.getElementById('cartCount');
        const addToCartButtons = document.querySelectorAll('.add-to-cart');
        const checkoutButton = document.getElementById('checkoutButton');
        
        // Open cart modal
        cartButton.addEventListener('click', (e) => {
            e.preventDefault();
            cartModal.style.display = 'block';
            updateCartDisplay();
        });
        
        // Close cart modal
        closeModal.addEventListener('click', () => {
            cartModal.style.display = 'none';
        });
        
        // Close modal when clicking outside
        window.addEventListener('click', (e) => {
            if (e.target === cartModal) {
                cartModal.style.display = 'none';
            }
        });
        
        // Add to cart functionality
        addToCartButtons.forEach(button => {
            button.addEventListener('click', () => {
                const id = button.getAttribute('data-id');
                const name = button.getAttribute('data-name');
                const price = parseFloat(button.getAttribute('data-price'));
                const image = button.getAttribute('data-image');
                
                // Check if item already in cart
                const existingItem = cart.find(item => item.id === id);
                
                if (existingItem) {
                    existingItem.quantity += 1;
                } else {
                    cart.push({
                        id,
                        name,
                        price,
                        image,
                        quantity: 1
                    });
                }
                
                updateCartCount();
                alert(`${name} added to cart!`);
            });
        });
        
        // Update cart count display
        function updateCartCount() {
            const totalItems = cart.reduce((total, item) => total + item.quantity, 0);
            cartCountElement.textContent = totalItems;
        }
        
        // Update cart display in modal
        function updateCartDisplay() {
            if (cart.length === 0) {
                cartItemsContainer.innerHTML = '<p>Your cart is empty</p>';
                cartTotalElement.textContent = 'Total: EGP 0.00';
                return;
            }
            
            let html = '';
            let total = 0;
            
            cart.forEach(item => {
                const itemTotal = item.price * item.quantity;
                total += itemTotal;
                
                html += `
                    <div class="cart-item">
                        <img src="${item.image}" alt="${item.name}">
                        <div class="cart-item-info">
                            <h4>${item.name}</h4>
                            <p>EGP ${item.price.toFixed(2)} × ${item.quantity}</p>
                        </div>
                        <div class="cart-item-price">
                            EGP ${itemTotal.toFixed(2)}
                        </div>
                    </div>
                `;
            });
            
            cartItemsContainer.innerHTML = html;
            cartTotalElement.textContent = `Total: EGP ${total.toFixed(2)}`;
        }
        
        // Checkout button
        checkoutButton.addEventListener('click', () => {
            if (cart.length === 0) {
                alert('Your cart is empty!');
                return;
            }
            
            // In a real implementation, this would redirect to a checkout page
            alert('Proceeding to checkout! In a real implementation, this would redirect to a payment page.');
        });
        
        // Contact form submission
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Thank you for your message! We will contact you soon.');
            this.reset();
        });
    </script>
</body>
</html>