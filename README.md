<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ayni Games - Tienda de Juegos de Mesa</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #6b2c3e 0%, #4a1f2c 100%);
            min-height: 100vh;
        }

        header {
            background: rgba(255, 255, 255, 0.98);
            padding: 1rem 2rem;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        nav {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .logo-container {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .logo-img {
            width: 60px;
            height: 60px;
            object-fit: contain;
            background: #f5f5f5;
            border-radius: 8px;
            padding: 5px;
        }

        .logo-text {
            display: flex;
            flex-direction: column;
        }

        .logo-title {
            font-size: 1.8rem;
            font-weight: bold;
            color: #6b2c3e;
            line-height: 1;
        }

        .logo-subtitle {
            font-size: 0.85rem;
            color: #333;
            letter-spacing: 2px;
            text-transform: uppercase;
        }

        .search-bar {
            flex: 1;
            max-width: 400px;
            position: relative;
        }

        .search-bar input {
            width: 100%;
            padding: 0.7rem 1rem;
            border: 2px solid #e0e0e0;
            border-radius: 25px;
            font-size: 1rem;
            transition: border-color 0.3s;
        }

        .search-bar input:focus {
            outline: none;
            border-color: #6b2c3e;
        }

        .cart-btn {
            background: #6b2c3e;
            color: white;
            padding: 0.6rem 1.5rem;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            transition: transform 0.3s, background 0.3s;
        }

        .cart-btn:hover {
            background: #4a1f2c;
            transform: scale(1.05);
        }

        .hero {
            max-width: 1400px;
            margin: 3rem auto;
            padding: 3rem 2rem;
            text-align: center;
            color: white;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.95;
        }

        .filter-section {
            max-width: 1400px;
            margin: 0 auto 2rem;
            padding: 0 2rem;
        }

        .filter-buttons {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            justify-content: center;
        }

        .filter-btn {
            background: white;
            border: 2px solid white;
            padding: 0.6rem 1.5rem;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            color: #333;
        }

        .filter-btn:hover, .filter-btn.active {
            background: #6b2c3e;
            color: white;
            border-color: white;
        }

        .products {
            max-width: 1400px;
            margin: 0 auto;
            padding: 2rem;
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 8px 20px rgba(0,0,0,0.15);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 12px 30px rgba(0,0,0,0.25);
        }

        .product-img {
            width: 100%;
            height: 250px;
            background: linear-gradient(135deg, #6b2c3e 0%, #4a1f2c 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1rem;
            color: white;
            font-weight: 600;
            text-align: center;
            padding: 1rem;
            position: relative;
        }

        .product-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: none;
        }

        .product-img.has-image img {
            display: block;
        }

        .product-img.has-image::before {
            display: none;
        }

        .upload-hint {
            position: absolute;
            bottom: 10px;
            right: 10px;
            background: rgba(0,0,0,0.6);
            padding: 5px 10px;
            border-radius: 10px;
            font-size: 0.75rem;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-title {
            font-size: 1.2rem;
            color: #333;
            margin-bottom: 0.5rem;
            font-weight: 700;
        }

        .product-category {
            display: inline-block;
            background: #f0f0f0;
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.8rem;
            color: #666;
            margin-bottom: 1rem;
        }

        .product-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 1rem;
        }

        .price {
            font-size: 1.5rem;
            font-weight: bold;
            color: #6b2c3e;
        }

        .buy-btn {
            background: #6b2c3e;
            color: white;
            border: none;
            padding: 0.7rem 1.5rem;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.3s, transform 0.2s;
        }

        .buy-btn:hover {
            background: #4a1f2c;
            transform: scale(1.05);
        }

        .no-results {
            text-align: center;
            color: white;
            font-size: 1.3rem;
            padding: 3rem;
        }

        /* Modal del carrito */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.7);
            animation: fadeIn 0.3s;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .modal-content {
            background-color: white;
            margin: 5% auto;
            padding: 2rem;
            border-radius: 15px;
            width: 90%;
            max-width: 600px;
            max-height: 80vh;
            overflow-y: auto;
            animation: slideIn 0.3s;
        }

        @keyframes slideIn {
            from { transform: translateY(-50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
            border-bottom: 2px solid #f0f0f0;
            padding-bottom: 1rem;
        }

        .modal-header h2 {
            color: #6b2c3e;
            font-size: 1.8rem;
        }

        .close-btn {
            background: none;
            border: none;
            font-size: 2rem;
            cursor: pointer;
            color: #999;
            transition: color 0.3s;
        }

        .close-btn:hover {
            color: #333;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem;
            border-bottom: 1px solid #f0f0f0;
        }

        .cart-item-info {
            flex: 1;
        }

        .cart-item-name {
            font-weight: 600;
            color: #333;
            margin-bottom: 0.3rem;
        }

        .cart-item-price {
            color: #6b2c3e;
            font-weight: bold;
        }

        .remove-btn {
            background: #ff4444;
            color: white;
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            cursor: pointer;
            font-size: 0.9rem;
            transition: background 0.3s;
        }

        .remove-btn:hover {
            background: #cc0000;
        }

        .cart-total {
            margin-top: 1.5rem;
            padding-top: 1.5rem;
            border-top: 2px solid #6b2c3e;
            text-align: right;
        }

        .cart-total-label {
            font-size: 1.3rem;
            color: #333;
            font-weight: 600;
        }

        .cart-total-price {
            font-size: 2rem;
            color: #6b2c3e;
            font-weight: bold;
            margin-top: 0.5rem;
        }

        .cart-actions {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
        }

        .whatsapp-btn {
            flex: 1;
            background: #25D366;
            color: white;
            border: none;
            padding: 1rem;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            font-size: 1.1rem;
            transition: background 0.3s, transform 0.2s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
        }

        .whatsapp-btn:hover {
            background: #128C7E;
            transform: scale(1.02);
        }

        .clear-cart-btn {
            background: #ff4444;
            color: white;
            border: none;
            padding: 1rem 1.5rem;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.3s;
        }

        .clear-cart-btn:hover {
            background: #cc0000;
        }

        .empty-cart {
            text-align: center;
            padding: 3rem;
            color: #999;
        }

        .empty-cart-icon {
            font-size: 4rem;
            margin-bottom: 1rem;
        }

        footer {
            background: rgba(0,0,0,0.4);
            color: white;
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .search-bar {
                max-width: 100%;
            }

            .logo-img {
                width: 50px;
                height: 50px;
            }

            .logo-title {
                font-size: 1.4rem;
            }

            .logo-subtitle {
                font-size: 0.7rem;
            }

            .modal-content {
                width: 95%;
                margin: 10% auto;
                padding: 1.5rem;
            }

            .cart-actions {
                flex-direction: column;
            }
        }

        @keyframes bounce {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <div class="logo-container">
                <!-- AQUÍ PUEDES PONER TU LOGO: Reemplaza el src="" con la URL de tu logo -->
    <img src="https://i.postimg.cc/661QNyqp/IMG-20251209-001629.png" alt="Ayni Games Logo" class="logo-img">
                <div class="logo-text">
                    <div class="logo-title">AYNI GAMES</div>
                    <div class="logo-subtitle">Juegos de Mesa</div>
                </div>
            </div>
            <div class="search-bar">
                <input type="text" id="searchInput" placeholder="Buscar juegos..." onkeyup="searchProducts()">
            </div>
            <button class="cart-btn" onclick="openCart()">🛒 Carrito (<span id="cartCount">0</span>)</button>
        </nav>
    </header>

    <section class="hero">
        <h1>Descubre la Magia de los Juegos de Mesa</h1>
        <p>Los mejores juegos para compartir momentos inolvidables con familia y amigos</p>
    </section>

    <section class="filter-section">
        <div class="filter-buttons">
            <button class="filter-btn active" onclick="filterProducts('todos')">Todos</button>
            <button class="filter-btn" onclick="filterProducts('cartas')">Juegos de Cartas</button>
            <button class="filter-btn" onclick="filterProducts('tablero')">Juegos de Tablero</button>
            <button class="filter-btn" onclick="filterProducts('estrategia')">Estrategia</button>
        </div>
    </section>

    <section class="products" id="productsContainer"></section>

    <!-- Modal del Carrito -->
    <div id="cartModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>🛒 Tu Carrito</h2>
                <button class="close-btn" onclick="closeCart()">&times;</button>
            </div>
            <div id="cartItems"></div>
            <div id="cartActions"></div>
        </div>
    </div>

    <footer>
        <p>&copy; 2025 Ayni Games - Tienda de Juegos de Mesa | Todos los derechos reservados</p>
        <p>📧 juegosdemesa.aynigames@gmail.com | 📞 +591 78933669</p>
    </footer>

    <script>
        // CONFIGURACIÓN - CAMBIA ESTE NÚMERO CON TU WHATSAPP
        const WHATSAPP_NUMBER = "59178933669"; // Pon tu número aquí (formato: código país + número sin +)

        const products = [
            {name: "7 Wonders Cartas", price: 335, category: "cartas"},
            {name: "7 Wonders Duel", price: 330, category: "estrategia"},
            {name: "7 Wonders Tablero", price: 690, category: "tablero"},
            {name: "Avalon", price: 230, category: "cartas"},
            {name: "Azul", price: 380, category: "tablero"},
            {name: "Azul Summer Pavillion", price: 410, category: "tablero"},
            {name: "Bears vs Babies", price: 240, category: "cartas"},
            {name: "Bears vs Babies EXP", price: 95, category: "cartas"},
            {name: "Beat That", price: 340, category: "tablero"},
            {name: "Breaking Kittens", price: 190, category: "cartas"},
            {name: "Carcassone", price: 360, category: "tablero"},
            {name: "Catan", price: 325, category: "estrategia"},
            {name: "Catan Extension", price: 290, category: "estrategia"},
            {name: "Catan Navegantes", price: 380, category: "estrategia"},
            {name: "Catan Navegantes Ext", price: 290, category: "estrategia"},
            {name: "Cities of Splendor", price: 360, category: "estrategia"},
            {name: "Clank", price: 500, category: "tablero"},
            {name: "Código Secreto", price: 280, category: "cartas"},
            {name: "Coup", price: 160, category: "cartas"},
            {name: "Dixit", price: 340, category: "cartas"},
            {name: "Dixit Quest EXP", price: 210, category: "cartas"},
            {name: "Dixit Stella", price: 360, category: "cartas"},
            {name: "EK Party", price: 190, category: "cartas"},
            {name: "Exploding Kittens", price: 175, category: "cartas"},
            {name: "Exploding Minions", price: 150, category: "cartas"},
            {name: "Fantasma Blitz", price: 150, category: "cartas"},
            {name: "Gatitos NSFW", price: 160, category: "cartas"},
            {name: "Happy Little Dinosaurs", price: 320, category: "cartas"},
            {name: "Happy Little Dinosaurs Expansion", price: 280, category: "cartas"},
            {name: "Hombre Lobo", price: 160, category: "cartas"},
            {name: "Imploding Streaking", price: 190, category: "cartas"},
            {name: "Jaipur", price: 230, category: "cartas"},
            {name: "Monopolio Games of Thrones", price: 390, category: "tablero"},
            {name: "Pandemic", price: 320, category: "estrategia"},
            {name: "Patchwork", price: 240, category: "tablero"},
            {name: "Phase 10", price: 50, category: "cartas"},
            {name: "Play Nine", price: 230, category: "cartas"},
            {name: "Race to the Treasure", price: 210, category: "tablero"},
            {name: "Root", price: 575, category: "estrategia"},
            {name: "Root Ribereños", price: 430, category: "estrategia"},
            {name: "Saboteur", price: 170, category: "cartas"},
            {name: "Secret Hitler", price: 350, category: "cartas"},
            {name: "Sequence", price: 260, category: "tablero"},
            {name: "Sequence for Kids", price: 230, category: "tablero"},
            {name: "Splendor", price: 350, category: "estrategia"},
            {name: "Splendor Marvel", price: 390, category: "estrategia"},
            {name: "Sushi GO Party", price: 320, category: "cartas"},
            {name: "Terraforming Mars", price: 690, category: "estrategia"},
            {name: "The Mind", price: 150, category: "cartas"},
            {name: "Ticket to Ride Europa", price: 360, category: "tablero"},
            {name: "Ticket to Ride for Journey", price: 320, category: "tablero"},
            {name: "Ticket to Ride USA", price: 360, category: "tablero"},
            {name: "Throw Throw Burrito", price: 380, category: "cartas"},
            {name: "Wingspan", price: 690, category: "estrategia"},
            {name: "Zombie Kittens", price: 170, category: "cartas"}
        ];

        let cart = [];
        let currentFilter = 'todos';

        const gradients = [
            'linear-gradient(135deg, #6b2c3e 0%, #8b3a4f 100%)',
            'linear-gradient(135deg, #8b3a4f 0%, #6b2c3e 100%)',
            'linear-gradient(135deg, #4a1f2c 0%, #6b2c3e 100%)',
            'linear-gradient(135deg, #6b2c3e 0%, #4a1f2c 100%)',
            'linear-gradient(135deg, #8b3a4f 0%, #4a1f2c 100%)',
            'linear-gradient(135deg, #4a1f2c 0%, #8b3a4f 100%)'
        ];

        function renderProducts(filteredProducts = products) {
            const container = document.getElementById('productsContainer');
            
            if (filteredProducts.length === 0) {
                container.innerHTML = '<div class="no-results">No se encontraron juegos 😢</div>';
                return;
            }

            container.innerHTML = filteredProducts.map((product, index) => `
                <div class="product-card">
                    <div class="product-img" style="background: ${gradients[index % gradients.length]}">
                        <img src="" alt="${product.name}" data-product="${product.name}">
                        ${product.name}
                        <div class="upload-hint">📷 Imagen próximamente</div>
                    </div>
                    <div class="product-info">
                        <h3 class="product-title">${product.name}</h3>
                        <span class="product-category">${getCategoryName(product.category)}</span>
                        <div class="product-footer">
                            <span class="price">Bs ${product.price}</span>
                            <button class="buy-btn" onclick="addToCart('${product.name.replace(/'/g, "\\'")}', ${product.price})">Comprar</button>
                        </div>
                    </div>
                </div>
            `).join('');
        }

        function getCategoryName(category) {
            const names = {
                'cartas': '🎴 Cartas',
                'tablero': '🎲 Tablero',
                'estrategia': '🧠 Estrategia'
            };
            return names[category] || '🎮 Juego';
        }

        function filterProducts(category) {
            currentFilter = category;
            
            document.querySelectorAll('.filter-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            event.target.classList.add('active');
            
            const filtered = category === 'todos' 
                ? products 
                : products.filter(p => p.category === category);
            
            renderProducts(filtered);
        }

        function searchProducts() {
            const searchTerm = document.getElementById('searchInput').value.toLowerCase();
            const filtered = products.filter(p => 
                p.name.toLowerCase().includes(searchTerm)
            );
            renderProducts(filtered);
        }

        function addToCart(productName, price) {
            cart.push({name: productName, price: price, id: Date.now()});
            updateCartCount();
            
            const cartBtn = document.querySelector('.cart-btn');
            cartBtn.style.animation = 'none';
            setTimeout(() => {
                cartBtn.style.animation = 'bounce 0.5s';
            }, 10);
        }

        function updateCartCount() {
            document.getElementById('cartCount').textContent = cart.length;
        }

        function removeFromCart(itemId) {
            cart = cart.filter(item => item.id !== itemId);
            updateCartCount();
            renderCart();
        }

        function clearCart() {
            if (confirm('¿Estás seguro de vaciar el carrito?')) {
                cart = [];
                updateCartCount();
                renderCart();
            }
        }

        function openCart() {
            document.getElementById('cartModal').style.display = 'block';
            renderCart();
        }

        function closeCart() {
            document.getElementById('cartModal').style.display = 'none';
        }

        function renderCart() {
            const cartItemsDiv = document.getElementById('cartItems');
            const cartActionsDiv = document.getElementById('cartActions');

            if (cart.length === 0) {
                cartItemsDiv.innerHTML = `
                    <div class="empty-cart">
                        <div class="empty-cart-icon">🛒</div>
                        <p>Tu carrito está vacío</p>
                    </div>
                `;
                cartActionsDiv.innerHTML = '';
                return;
            }

            const total = cart.reduce((sum, item) => sum + item.price, 0);

            cartItemsDiv.innerHTML = cart.map(item => `
                <div class="cart-item">
                    <div class="cart-item-info">
                        <div class="cart-item-name">${item.name}</div>
                        <div class="cart-item-price">Bs ${item.price}</div>
                    </div>
                    <button class="remove-btn" onclick="removeFromCart(${item.id})">Eliminar</button>
                </div>
            `).join('');

            cartActionsDiv.innerHTML = `
                <div class="cart-total">
                    <div class="cart-total-label">Total:</div>
                    <div class="cart-total-price">Bs ${total}</div>
                </div>
                <div class="cart-actions">
                    <button class="whatsapp-btn" onclick="sendToWhatsApp()">
                        <span style="font-size: 1.5rem;">📱</span>
                        Enviar Pedido por WhatsApp
                    </button>
                    <button class="clear-cart-btn" onclick="clearCart()">Vaciar</button>
                </div>
            `;
        }

        function sendToWhatsApp() {
            if (cart.length === 0) {
                alert('El carrito está vacío');
                return;
            }

            const total = cart.reduce((sum, item) => sum + item.price, 0);
            
            let message = '🎲 *PEDIDO AYNI GAMES*\n\n';
            message += '📋 *Productos:*\n';
            
            cart.forEach((item, index) => {
                message += `${index + 1}. ${item.name} - Bs ${item.price}\n`;
            });
            
            message += `\n💰 *TOTAL: Bs ${total}*\n\n`;
            message += '¡Pedido finalizado! 🙌';

            const whatsappUrl = `https://wa.me/${WHATSAPP_NUMBER}?text=${encodeURIComponent(message)}`;
            window.open(whatsappUrl, '_blank');
        }

        // Cerrar modal al hacer clic fuera
        window.onclick = function(event) {
            const modal = document.getElementById('cartModal');
            if (event.target == modal) {
                closeCart();
            }
        }

        renderProducts();
    </script>
</body>
</html>
