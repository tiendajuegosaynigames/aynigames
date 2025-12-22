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
