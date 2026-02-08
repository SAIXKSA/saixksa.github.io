
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تك ستور - متجر قطع الكمبيوتر المتخصص</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/lucide/0.263.1/umd/lucide.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            background: white;
            padding: 20px 30px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            margin-bottom: 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        .logo-section {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #0f2027 0%, #203a43 50%, #2c5364 100%);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 32px;
            box-shadow: 0 8px 20px rgba(15, 32, 39, 0.4);
            position: relative;
            overflow: hidden;
        }

        .logo::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .logo-icon {
            position: relative;
            z-index: 1;
            filter: drop-shadow(0 2px 4px rgba(0,0,0,0.3));
        }

        .logo-text {
            display: flex;
            flex-direction: column;
        }

        .logo-title {
            font-size: 28px;
            font-weight: bold;
            background: linear-gradient(135deg, #0f2027 0%, #2c5364 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -1px;
        }

        .logo-subtitle {
            font-size: 12px;
            color: #636e72;
            font-weight: 500;
        }

        .header-actions {
            display: flex;
            gap: 15px;
            align-items: center;
        }

        .user-btn, .cart-btn {
            background: #667eea;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 25px;
            display: flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
            font-size: 16px;
            font-weight: bold;
            transition: all 0.3s;
        }

        .user-btn:hover, .cart-btn:hover {
            background: #5568d3;
            transform: translateY(-2px);
        }

        .cart-count {
            background: #ff4757;
            color: white;
            border-radius: 50%;
            width: 24px;
            height: 24px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 12px;
            font-weight: bold;
        }

        .search-bar {
            width: 100%;
            max-width: 600px;
            position: relative;
            margin: 0 20px;
        }

        .search-bar input {
            width: 100%;
            padding: 12px 45px 12px 20px;
            border: 2px solid #e0e0e0;
            border-radius: 25px;
            font-size: 16px;
            transition: all 0.3s;
        }

        .search-bar input:focus {
            outline: none;
            border-color: #667eea;
        }

        .search-icon {
            position: absolute;
            left: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: #667eea;
        }

        .categories {
            display: flex;
            gap: 15px;
            margin-bottom: 30px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .category-btn {
            background: white;
            border: 2px solid white;
            padding: 12px 25px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            transition: all 0.3s;
            color: #667eea;
        }

        .category-btn:hover, .category-btn.active {
            background: #667eea;
            color: white;
            transform: translateY(-2px);
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 25px;
            margin-bottom: 30px;
        }

        .product-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: all 0.3s;
            cursor: pointer;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        .product-image {
            width: 100%;
            height: 220px;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            position: relative;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .product-image.gpu {
            background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);
        }

        .product-image.cpu {
            background: linear-gradient(135deg, #ee0979 0%, #ff6a00 100%);
        }

        .product-image.ram {
            background: linear-gradient(135deg, #4776e6 0%, #8e54e9 100%);
        }

        .product-image.storage {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .product-image.motherboard {
            background: linear-gradient(135deg, #fa709a 0%, #fee140 100%);
        }

        .product-image.cooling {
            background: linear-gradient(135deg, #30cfd0 0%, #330867 100%);
        }

        .product-image.psu {
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
        }

        .product-placeholder {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: white;
            text-align: center;
            padding: 20px;
        }

        .product-placeholder-icon {
            font-size: 80px;
            margin-bottom: 10px;
            filter: drop-shadow(0 4px 8px rgba(0,0,0,0.3));
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .product-placeholder-text {
            font-size: 14px;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 2px;
            opacity: 0.9;
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .product-info {
            padding: 20px;
        }

        .product-brand {
            color: #667eea;
            font-size: 12px;
            font-weight: bold;
            text-transform: uppercase;
            margin-bottom: 5px;
        }

        .product-name {
            font-size: 18px;
            font-weight: bold;
            color: #2d3436;
            margin-bottom: 10px;
        }

        .product-rating {
            display: flex;
            align-items: center;
            gap: 5px;
            margin-bottom: 10px;
        }

        .stars {
            color: #f39c12;
            font-size: 16px;
        }

        .rating-count {
            color: #636e72;
            font-size: 14px;
        }

        .product-price {
            font-size: 28px;
            font-weight: bold;
            color: #667eea;
            margin-bottom: 15px;
        }

        .add-to-cart-btn {
            width: 100%;
            background: #667eea;
            color: white;
            border: none;
            padding: 12px;
            border-radius: 10px;
            cursor: pointer;
            font-size: 16px;
            font-weight: bold;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .add-to-cart-btn:hover {
            background: #5568d3;
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.7);
            z-index: 1000;
            align-items: center;
            justify-content: center;
            padding: 20px;
            overflow-y: auto;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: white;
            border-radius: 15px;
            padding: 30px;
            max-width: 900px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
        }

        .close-modal {
            position: absolute;
            top: 20px;
            left: 20px;
            background: none;
            border: none;
            font-size: 28px;
            cursor: pointer;
            color: #636e72;
            width: 32px;
            height: 32px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .product-detail-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-top: 30px;
        }

        .product-detail-image {
            width: 100%;
            height: 400px;
            border-radius: 10px;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .product-detail-image.gpu {
            background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);
        }

        .product-detail-image.cpu {
            background: linear-gradient(135deg, #ee0979 0%, #ff6a00 100%);
        }

        .product-detail-image.ram {
            background: linear-gradient(135deg, #4776e6 0%, #8e54e9 100%);
        }

        .product-detail-image.storage {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .product-detail-image.motherboard {
            background: linear-gradient(135deg, #fa709a 0%, #fee140 100%);
        }

        .product-detail-image.cooling {
            background: linear-gradient(135deg, #30cfd0 0%, #330867 100%);
        }

        .product-detail-image.psu {
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
        }

        .product-detail-image img {
            width: 100%;
            height: 100%;
            object-fit: contain;
        }

        .product-detail-info h2 {
            color: #2d3436;
            margin-bottom: 10px;
        }

        .product-detail-price {
            font-size: 32px;
            font-weight: bold;
            color: #667eea;
            margin: 15px 0;
        }

        .specs-section {
            margin: 20px 0;
        }

        .specs-section h3 {
            color: #2d3436;
            margin-bottom: 15px;
            font-size: 18px;
        }

        .spec-item {
            display: flex;
            padding: 10px 0;
            border-bottom: 1px solid #e0e0e0;
        }

        .spec-label {
            font-weight: bold;
            color: #636e72;
            min-width: 150px;
        }

        .spec-value {
            color: #2d3436;
        }

        .reviews-section {
            margin-top: 30px;
            padding-top: 30px;
            border-top: 2px solid #e0e0e0;
        }

        .reviews-section h3 {
            color: #2d3436;
            margin-bottom: 20px;
        }

        .review-item {
            padding: 15px;
            background: #f5f7fa;
            border-radius: 10px;
            margin-bottom: 15px;
        }

        .review-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }

        .reviewer-name {
            font-weight: bold;
            color: #2d3436;
        }

        .review-date {
            color: #636e72;
            font-size: 14px;
        }

        .review-stars {
            color: #f39c12;
            margin-bottom: 10px;
        }

        .review-text {
            color: #2d3436;
            line-height: 1.6;
        }

        /* Login Modal */
        .login-content {
            max-width: 450px;
        }

        .login-header {
            text-align: center;
            margin-bottom: 30px;
        }

        .login-header h2 {
            color: #667eea;
            margin-bottom: 10px;
        }

        .login-form input {
            width: 100%;
            padding: 12px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-size: 16px;
            margin-bottom: 15px;
        }

        .login-form input:focus {
            outline: none;
            border-color: #667eea;
        }

        .login-btn {
            width: 100%;
            background: #667eea;
            color: white;
            border: none;
            padding: 15px;
            border-radius: 10px;
            cursor: pointer;
            font-size: 18px;
            font-weight: bold;
            margin-top: 10px;
        }

        .login-btn:hover {
            background: #5568d3;
        }

        .verification-code {
            text-align: center;
            padding: 20px;
            background: #f5f7fa;
            border-radius: 10px;
            margin: 20px 0;
        }

        .verification-code-display {
            font-size: 32px;
            font-weight: bold;
            color: #667eea;
            letter-spacing: 8px;
            margin: 15px 0;
        }

        /* Cart Styles */
        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
            padding-bottom: 15px;
            border-bottom: 2px solid #e0e0e0;
        }

        .cart-header h2 {
            color: #667eea;
            font-size: 24px;
        }

        .cart-item {
            display: flex;
            gap: 15px;
            padding: 15px;
            border-bottom: 1px solid #e0e0e0;
            align-items: center;
        }

        .cart-item-image {
            width: 80px;
            height: 80px;
            border-radius: 8px;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .cart-item-image.gpu {
            background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);
        }

        .cart-item-image.cpu {
            background: linear-gradient(135deg, #ee0979 0%, #ff6a00 100%);
        }

        .cart-item-image.ram {
            background: linear-gradient(135deg, #4776e6 0%, #8e54e9 100%);
        }

        .cart-item-image.storage {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .cart-item-image.motherboard {
            background: linear-gradient(135deg, #fa709a 0%, #fee140 100%);
        }

        .cart-item-image.cooling {
            background: linear-gradient(135deg, #30cfd0 0%, #330867 100%);
        }

        .cart-item-image.psu {
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
        }

        .cart-item-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .cart-item-details {
            flex: 1;
        }

        .cart-item-name {
            font-weight: bold;
            color: #2d3436;
            margin-bottom: 5px;
        }

        .cart-item-price {
            color: #667eea;
            font-weight: bold;
        }

        .cart-item-controls {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .qty-btn {
            background: #667eea;
            color: white;
            border: none;
            width: 28px;
            height: 28px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 18px;
        }

        .qty-display {
            font-weight: bold;
            min-width: 30px;
            text-align: center;
        }

        .remove-btn {
            background: #ff4757;
            color: white;
            border: none;
            padding: 6px 12px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 12px;
        }

        .cart-total {
            margin-top: 20px;
            padding-top: 20px;
            border-top: 2px solid #e0e0e0;
            font-size: 22px;
            font-weight: bold;
            color: #2d3436;
            text-align: left;
        }

        .cart-total span {
            color: #667eea;
        }

        /* Payment Methods */
        .payment-section {
            margin: 20px 0;
        }

        .payment-section h3 {
            color: #2d3436;
            margin-bottom: 15px;
        }

        .payment-methods {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        .payment-method {
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            padding: 15px 25px;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .payment-method:hover, .payment-method.selected {
            border-color: #667eea;
            background: #f5f7fa;
        }

        .payment-icon {
            font-size: 32px;
        }

        .payment-name {
            font-weight: bold;
            color: #2d3436;
        }

        .checkout-btn {
            width: 100%;
            background: #00b894;
            color: white;
            border: none;
            padding: 15px;
            border-radius: 10px;
            cursor: pointer;
            font-size: 18px;
            font-weight: bold;
            margin-top: 20px;
        }

        .checkout-btn:hover {
            background: #00a383;
        }

        .checkout-btn:disabled {
            background: #b2bec3;
            cursor: not-allowed;
        }

        .empty-cart {
            text-align: center;
            padding: 40px 20px;
            color: #636e72;
        }

        .notification {
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            background: #00b894;
            color: white;
            padding: 15px 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            z-index: 2000;
            display: none;
            animation: slideDown 0.3s ease;
        }

        .notification.show {
            display: block;
        }

        @keyframes slideDown {
            from {
                transform: translate(-50%, -100%);
                opacity: 0;
            }
            to {
                transform: translate(-50%, 0);
                opacity: 1;
            }
        }

        /* Product Page Styles */
        #productPage {
            display: none;
        }

        .product-page-header {
            background: white;
            padding: 20px 30px;
            border-radius: 15px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .back-btn {
            background: #667eea;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 25px;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
            font-size: 16px;
            font-weight: bold;
            transition: all 0.3s;
            margin-bottom: 15px;
        }

        .back-btn:hover {
            background: #5568d3;
            transform: translateX(5px);
        }

        .breadcrumb {
            color: #636e72;
            font-size: 14px;
        }

        .product-page-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            background: white;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            margin-bottom: 30px;
        }

        .product-page-image {
            width: 100%;
            height: 500px;
            border-radius: 15px;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .product-page-image.gpu {
            background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);
        }

        .product-page-image.cpu {
            background: linear-gradient(135deg, #ee0979 0%, #ff6a00 100%);
        }

        .product-page-image.ram {
            background: linear-gradient(135deg, #4776e6 0%, #8e54e9 100%);
        }

        .product-page-image.storage {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .product-page-image.motherboard {
            background: linear-gradient(135deg, #fa709a 0%, #fee140 100%);
        }

        .product-page-image.cooling {
            background: linear-gradient(135deg, #30cfd0 0%, #330867 100%);
        }

        .product-page-image.psu {
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
        }

        .product-page-title {
            font-size: 32px;
            color: #2d3436;
            margin: 15px 0;
        }

        .product-page-price {
            font-size: 36px;
            font-weight: bold;
            color: #667eea;
            margin: 20px 0;
        }

        .product-actions {
            display: flex;
            gap: 15px;
            margin: 30px 0;
        }

        .add-to-cart-btn-large {
            flex: 1;
            background: #667eea;
            color: white;
            border: none;
            padding: 18px;
            border-radius: 12px;
            cursor: pointer;
            font-size: 18px;
            font-weight: bold;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            transition: all 0.3s;
        }

        .add-to-cart-btn-large:hover {
            background: #5568d3;
            transform: translateY(-2px);
        }

        .buy-now-btn {
            flex: 1;
            background: #00b894;
            color: white;
            border: none;
            padding: 18px;
            border-radius: 12px;
            cursor: pointer;
            font-size: 18px;
            font-weight: bold;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            transition: all 0.3s;
        }

        .buy-now-btn:hover {
            background: #00a383;
            transform: translateY(-2px);
        }

        .reviews-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
        }

        .related-products {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .related-products h3 {
            color: #2d3436;
            margin-bottom: 25px;
            font-size: 24px;
        }

        .related-products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 20px;
        }

        .product-card-small {
            background: #f5f7fa;
            border-radius: 12px;
            padding: 15px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .product-card-small:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .product-image-small {
            width: 100%;
            height: 150px;
            border-radius: 10px;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .product-image-small.gpu {
            background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);
        }

        .product-image-small.cpu {
            background: linear-gradient(135deg, #ee0979 0%, #ff6a00 100%);
        }

        .product-image-small.ram {
            background: linear-gradient(135deg, #4776e6 0%, #8e54e9 100%);
        }

        .product-image-small.storage {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .product-image-small.motherboard {
            background: linear-gradient(135deg, #fa709a 0%, #fee140 100%);
        }

        .product-image-small.cooling {
            background: linear-gradient(135deg, #30cfd0 0%, #330867 100%);
        }

        .product-image-small.psu {
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
        }

        .product-name-small {
            font-size: 14px;
            font-weight: bold;
            color: #2d3436;
            margin-bottom: 5px;
        }

        .product-price-small {
            font-size: 16px;
            font-weight: bold;
            color: #667eea;
        }

        @media (max-width: 768px) {
            .product-page-grid {
                grid-template-columns: 1fr;
                padding: 20px;
            }

            .product-actions {
                flex-direction: column;
            }

            .related-products-grid {
                grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            }
        }

        /* Admin Panel Styles */
        .admin-access-btn {
            position: fixed;
            bottom: 20px;
            left: 20px;
            width: 50px;
            height: 50px;
            background: #2d3436;
            border: none;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 12px rgba(0,0,0,0.3);
            transition: all 0.3s;
            z-index: 999;
            opacity: 0.3;
        }

        .admin-access-btn:hover {
            opacity: 1;
            transform: scale(1.1);
        }

        .admin-access-btn i {
            color: white;
        }

        .admin-panel {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.8);
            z-index: 10000;
            overflow-y: auto;
        }

        .admin-panel.active {
            display: block;
        }

        .admin-content {
            max-width: 1200px;
            margin: 50px auto;
            background: white;
            border-radius: 15px;
            padding: 30px;
        }

        .admin-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 2px solid #e0e0e0;
        }

        .admin-header h2 {
            color: #2d3436;
        }

        .close-admin {
            background: #ff4757;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
        }

        .admin-products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
        }

        .admin-product-card {
            background: #f5f7fa;
            border-radius: 12px;
            padding: 20px;
            border: 2px solid transparent;
            transition: all 0.3s;
        }

        .admin-product-card:hover {
            border-color: #667eea;
        }

        .admin-images-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 10px;
            margin-bottom: 15px;
        }

        .admin-image-item {
            position: relative;
        }

        .image-controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 5px;
            gap: 5px;
        }

        .image-number {
            font-size: 11px;
            color: #636e72;
            font-weight: bold;
        }

        .remove-single-image-btn {
            background: #ff4757;
            color: white;
            border: none;
            padding: 4px 8px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 11px;
            font-weight: bold;
            transition: all 0.3s;
        }

        .remove-single-image-btn:hover {
            background: #ee5a6f;
        }

        .remove-all-images-btn {
            width: 100%;
            background: #ff6b81;
            color: white;
            border: none;
            padding: 10px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            margin-top: 10px;
            transition: all 0.3s;
        }

        .remove-all-images-btn:hover {
            background: #ee5a6f;
        }

        .add-image-section {
            margin-top: 15px;
        }

        /* Image Gallery Styles */
        .product-gallery-container {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .main-product-image {
            width: 100%;
            height: 400px;
            border-radius: 15px;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }

        .gallery-thumbnails {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
            gap: 10px;
        }

        .gallery-thumbnail {
            width: 100%;
            height: 80px;
            border-radius: 8px;
            overflow: hidden;
            cursor: pointer;
            border: 3px solid transparent;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .gallery-thumbnail:hover {
            border-color: #667eea;
            transform: scale(1.05);
        }

        .gallery-thumbnail.active {
            border-color: #667eea;
        }

        .gallery-thumbnail img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .gallery-thumbnail.gpu {
            background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);
        }

        .gallery-thumbnail.cpu {
            background: linear-gradient(135deg, #ee0979 0%, #ff6a00 100%);
        }

        .gallery-thumbnail.ram {
            background: linear-gradient(135deg, #4776e6 0%, #8e54e9 100%);
        }

        .gallery-thumbnail.storage {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .gallery-thumbnail.motherboard {
            background: linear-gradient(135deg, #fa709a 0%, #fee140 100%);
        }

        .gallery-thumbnail.cooling {
            background: linear-gradient(135deg, #30cfd0 0%, #330867 100%);
        }

        .gallery-thumbnail.psu {
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
        }

        /* Educational Banner */
        .educational-banner {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 15px;
            padding: 40px;
            margin-bottom: 30px;
            color: white;
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.3);
        }

        .banner-content h2 {
            font-size: 32px;
            margin-bottom: 15px;
        }

        .banner-content p {
            font-size: 18px;
            margin-bottom: 25px;
            opacity: 0.9;
        }

        .banner-actions {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        .banner-btn {
            background: white;
            color: #667eea;
            border: none;
            padding: 15px 30px;
            border-radius: 10px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
        }

        .banner-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .banner-btn.secondary {
            background: rgba(255,255,255,0.2);
            color: white;
        }

        /* PC Builder Styles */
        #pcBuilderPage {
            display: none;
        }

        .builder-header {
            background: white;
            padding: 30px;
            border-radius: 15px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .builder-header h2 {
            color: #2d3436;
            margin: 15px 0 10px 0;
            font-size: 28px;
        }

        .builder-header p {
            color: #636e72;
            font-size: 16px;
        }

        .builder-grid {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 30px;
        }

        .builder-components {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .component-selector {
            background: white;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
        }

        .component-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }

        .component-title {
            font-size: 18px;
            font-weight: bold;
            color: #2d3436;
        }

        .component-required {
            color: #ff4757;
            font-size: 12px;
            font-weight: bold;
        }

        .component-select {
            width: 100%;
            padding: 12px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
        }

        .component-select:focus {
            outline: none;
            border-color: #667eea;
        }

        .component-info {
            margin-top: 10px;
            padding: 10px;
            background: #f5f7fa;
            border-radius: 6px;
            font-size: 14px;
            color: #636e72;
        }

        .builder-summary {
            background: white;
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 20px;
            max-height: calc(100vh - 40px);
            overflow-y: auto;
        }

        .builder-summary h3 {
            color: #2d3436;
            margin-bottom: 20px;
        }

        .summary-item {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-bottom: 1px solid #e0e0e0;
        }

        .summary-label {
            color: #636e72;
            font-weight: 600;
        }

        .summary-value {
            color: #2d3436;
            font-weight: bold;
        }

        .builder-total {
            display: flex;
            justify-content: space-between;
            padding: 20px 0;
            margin-top: 20px;
            border-top: 2px solid #667eea;
            font-size: 24px;
            font-weight: bold;
            color: #667eea;
        }

        .add-build-to-cart-btn {
            width: 100%;
            background: #00b894;
            color: white;
            border: none;
            padding: 15px;
            border-radius: 10px;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            margin-top: 20px;
            transition: all 0.3s;
        }

        .add-build-to-cart-btn:hover:not(:disabled) {
            background: #00a383;
        }

        .add-build-to-cart-btn:disabled {
            background: #b2bec3;
            cursor: not-allowed;
        }

        #compatibilityCheck {
            background: #fff3cd;
            border: 2px solid #ffc107;
            border-radius: 8px;
            padding: 15px;
            margin: 20px 0;
        }

        #compatibilityCheck h4 {
            color: #856404;
            margin-bottom: 10px;
        }

        .compatibility-issue {
            color: #856404;
            padding: 5px 0;
            font-size: 14px;
        }

        @media (max-width: 968px) {
            .builder-grid {
                grid-template-columns: 1fr;
            }

            .builder-summary {
                position: relative;
                top: 0;
            }
        }



        .admin-product-image {
            width: 100%;
            height: 200px;
            border-radius: 10px;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        .admin-product-name {
            font-weight: bold;
            color: #2d3436;
            margin-bottom: 10px;
        }

        .image-url-input {
            width: 100%;
            padding: 10px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            margin-bottom: 10px;
            font-size: 14px;
        }

        .image-url-input:focus {
            outline: none;
            border-color: #667eea;
        }

        .save-image-btn {
            width: 100%;
            background: #00b894;
            color: white;
            border: none;
            padding: 12px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s;
        }

        .save-image-btn:hover {
            background: #00a383;
        }

        .remove-image-btn {
            width: 100%;
            background: #ff4757;
            color: white;
            border: none;
            padding: 10px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            margin-top: 5px;
            transition: all 0.3s;
        }

        .remove-image-btn:hover {
            background: #ee5a6f;
        }

        .admin-login {
            max-width: 400px;
            margin: 100px auto;
            background: white;
            padding: 40px;
            border-radius: 15px;
            text-align: center;
        }

        .admin-login h2 {
            color: #2d3436;
            margin-bottom: 20px;
        }

        .admin-password-input {
            width: 100%;
            padding: 15px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-size: 16px;
            margin-bottom: 15px;
        }

        .admin-password-input:focus {
            outline: none;
            border-color: #667eea;
        }

        .admin-login-btn {
            width: 100%;
            background: #667eea;
            color: white;
            border: none;
            padding: 15px;
            border-radius: 10px;
            cursor: pointer;
            font-size: 18px;
            font-weight: bold;
        }

        .admin-login-btn:hover {
            background: #5568d3;
        }

        .image-preview {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .upload-instructions {
            background: #fff3cd;
            border: 1px solid #ffc107;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 20px;
        }

        .upload-instructions h4 {
            color: #856404;
            margin-bottom: 10px;
        }

        .upload-instructions p {
            color: #856404;
            font-size: 14px;
            line-height: 1.6;
        }

    </style>
</head>
<body>
    <div class="notification" id="notification"></div>

    <div class="container">
        <header>
            <div class="logo-section">
                <div class="logo">
                    <span class="logo-icon">⚡</span>
                </div>
                <div class="logo-text">
                    <div class="logo-title">تك ستور</div>
                    <div class="logo-subtitle">متخصصون في قطع الكمبيوتر</div>
                </div>
            </div>
            <div class="search-bar">
                <input type="text" id="searchInput" placeholder="ابحث عن القطعة المناسبة...">
                <i data-lucide="search" class="search-icon"></i>
            </div>
            <div class="header-actions">
                <button class="user-btn" id="userBtn">
                    <i data-lucide="user"></i>
                    <span id="userBtnText">تسجيل الدخول</span>
                </button>
                <button class="cart-btn" id="cartBtn">
                    <i data-lucide="shopping-cart"></i>
                    <span>السلة</span>
                    <div class="cart-count" id="cartCount">0</div>
                </button>
            </div>
        </header>

        <!-- Home Page -->
        <div id="homePage">
            <!-- Educational Banner -->
            <div class="educational-banner">
                <div class="banner-content">
                    <h2>🎓 دليلك الشامل لبناء الكمبيوتر</h2>
                    <p>نساعدك في اختيار القطع المناسبة بناءً على احتياجاتك وميزانيتك</p>
                    <div class="banner-actions">
                        <button class="banner-btn" onclick="navigateToPCBuilder()">
                            🔧 أداة بناء الكمبيوتر
                        </button>
                        <button class="banner-btn secondary" onclick="showBuyingGuide()">
                            📖 دليل الشراء
                        </button>
                    </div>
                </div>
            </div>

            <div class="categories">
                <button class="category-btn active" data-category="all">الكل</button>
                <button class="category-btn" data-category="cpu">معالجات</button>
                <button class="category-btn" data-category="gpu">كروت شاشة</button>
                <button class="category-btn" data-category="ram">ذاكرة RAM</button>
                <button class="category-btn" data-category="storage">تخزين</button>
                <button class="category-btn" data-category="motherboard">لوحات أم</button>
                <button class="category-btn" data-category="cooling">تبريد</button>
                <button class="category-btn" data-category="psu">مزودات طاقة</button>
            </div>

            <div class="products-grid" id="productsGrid"></div>
        </div>

        <!-- Product Page -->
        <div id="productPage">
            <div id="productPageContent"></div>
        </div>

        <!-- PC Builder Page -->
        <div id="pcBuilderPage" style="display: none;">
            <div class="builder-header">
                <button class="back-btn" onclick="navigateToHome()">
                    <i data-lucide="arrow-right"></i>
                    <span>العودة للرئيسية</span>
                </button>
                <h2>🔧 أداة بناء الكمبيوتر الذكية</h2>
                <p>اختر القطع وسنتحقق من التوافق تلقائياً</p>
            </div>

            <div class="builder-grid">
                <div class="builder-components">
                    <div id="builderComponentsList"></div>
                </div>

                <div class="builder-summary">
                    <h3>📊 ملخص البناء</h3>
                    <div id="builderSummary"></div>
                    
                    <div id="compatibilityCheck" style="display: none;">
                        <h4>⚠️ تحذيرات التوافق</h4>
                        <div id="compatibilityIssues"></div>
                    </div>
                    
                    <div class="builder-total">
                        <div>الإجمالي:</div>
                        <div id="builderTotal">0 ريال</div>
                    </div>
                    
                    <button class="add-build-to-cart-btn" onclick="addBuildToCart()" id="addBuildBtn" disabled>
                        أضف الجهاز للسلة
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Compare Bar -->
    <div class="compare-bar" id="compareBar">
        <div class="compare-bar-content">
            <div class="compare-items" id="compareItems"></div>
            <div class="compare-actions">
                <button class="compare-action-btn primary" onclick="showComparison()">مقارنة (<span id="compareCount">0</span>)</button>
                <button class="compare-action-btn secondary" onclick="clearComparison()">مسح الكل</button>
            </div>
        </div>
    </div>

    <!-- Admin Access Button -->
    <button class="admin-access-btn" id="adminAccessBtn" title="لوحة التحكم">
        <i data-lucide="settings"></i>
    </button>

    <!-- Admin Panel -->
    <div class="admin-panel" id="adminPanel">
        <div id="adminLoginScreen" class="admin-login">
            <h2>🔐 تسجيل دخول الإدارة</h2>
            <p style="color: #636e72; margin-bottom: 20px;">أدخل كلمة المرور للوصول إلى لوحة التحكم</p>
            <input type="password" id="adminPasswordInput" class="admin-password-input" placeholder="كلمة المرور" />
            <button class="admin-login-btn" id="adminLoginBtn">دخول</button>
            <p style="color: #636e72; font-size: 12px; margin-top: 15px;">كلمة المرور الافتراضية: admin123</p>
        </div>

        <div id="adminDashboard" style="display: none;">
            <div class="admin-content">
                <div class="admin-header">
                    <h2>🎨 لوحة تحكم المنتجات</h2>
                    <button class="close-admin" id="closeAdmin">إغلاق ✕</button>
                </div>

                <div class="upload-instructions">
                    <h4>📸 كيفية إضافة صور متعددة:</h4>
                    <p>
                        1. ارفع الصورة على موقع مثل <strong>imgur.com</strong> أو <strong>postimages.org</strong><br>
                        2. انسخ رابط الصورة المباشر (يجب أن ينتهي بـ .jpg أو .png)<br>
                        3. الصق الرابط في الخانة أدناه واضغط "إضافة صورة"<br>
                        4. كرر العملية لإضافة صور إضافية لنفس المنتج<br>
                        5. يمكنك حذف أي صورة بشكل فردي أو حذف جميع الصور دفعة واحدة<br>
                        6. الصورة الأولى ستظهر في الصفحة الرئيسية وباقي الصور في معرض المنتج
                    </p>
                </div>

                <div class="admin-products-grid" id="adminProductsGrid"></div>
            </div>
        </div>
    </div>

    <!-- Product Detail Modal - Kept for backward compatibility but hidden -->
    <div class="modal" id="productModal" style="display: none !important;">
        <div class="modal-content">
            <button class="close-modal" id="closeProduct">×</button>
            <div id="productDetail"></div>
        </div>
    </div>

    <!-- Login Modal -->
    <div class="modal" id="loginModal">
        <div class="modal-content login-content">
            <button class="close-modal" id="closeLogin">×</button>
            <div class="login-header">
                <h2>تسجيل الدخول</h2>
                <p style="color: #636e72;">أدخل بريدك الإلكتروني للمتابعة</p>
            </div>
            <div class="login-form">
                <input type="email" id="emailInput" placeholder="البريد الإلكتروني" />
                <div id="verificationSection" style="display: none;">
                    <div class="verification-code">
                        <p style="color: #636e72; margin-bottom: 10px;">تم إرسال كود التحقق إلى بريدك</p>
                        <div class="verification-code-display" id="verificationCode"></div>
                        <p style="color: #636e72; font-size: 12px; margin-top: 10px;">أدخل هذا الكود أدناه للتحقق</p>
                    </div>
                    <input type="text" id="codeInput" placeholder="أدخل كود التحقق" maxlength="6" />
                </div>
                <button class="login-btn" id="loginBtn">إرسال كود التحقق</button>
            </div>
        </div>
    </div>

    <!-- Cart Modal -->
    <div class="modal" id="cartModal">
        <div class="modal-content">
            <button class="close-modal" id="closeCart">×</button>
            <div class="cart-header">
                <h2>سلة المشتريات</h2>
            </div>
            <div id="cartItems"></div>
            <div class="payment-section" id="paymentSection" style="display: none;">
                <h3>اختر طريقة الدفع</h3>
                <div class="payment-methods">
                    <div class="payment-method" data-payment="visa">
                        <div class="payment-icon">💳</div>
                        <div class="payment-name">Visa</div>
                    </div>
                    <div class="payment-method" data-payment="mastercard">
                        <div class="payment-icon">💳</div>
                        <div class="payment-name">MasterCard</div>
                    </div>
                    <div class="payment-method" data-payment="mada">
                        <div class="payment-icon">🏧</div>
                        <div class="payment-name">مدى</div>
                    </div>
                </div>
            </div>
            <div class="cart-total" id="cartTotal" style="display: none;">
                الإجمالي: <span id="totalAmount">0</span> ريال
            </div>
            <button class="checkout-btn" id="checkoutBtn" style="display: none;">إتمام الشراء</button>
        </div>
    </div>

    <script>
        const products = [
            {
                id: 1,
                name: 'NVIDIA GeForce RTX 4060',
                brand: 'NVIDIA',
                category: 'gpu',
                price: 1899,
                icon: '🎮',
                image: 'https://images.unsplash.com/photo-1591488320449-011701bb6704?w=800&q=80',
                rating: 4.5,
                reviews: 156,
                specs: {
                    'نوع الذاكرة': 'GDDR6',
                    'حجم الذاكرة': '8 GB',
                    'سرعة المعالج': '2310 MHz',
                    'استهلاك الطاقة': '115W',
                    'المنافذ': 'HDMI 2.1, DisplayPort 1.4a',
                    'التبريد': 'مروحتين'
                },
                customerReviews: [
                    { name: 'أحمد محمد', date: '2026-01-15', rating: 5, text: 'كرت ممتاز جداً للألعاب، الأداء رهيب والسعر معقول' },
                    { name: 'سارة علي', date: '2026-01-10', rating: 4, text: 'جودة عالية وتبريد ممتاز، ينصح به بشدة' }
                ]
            },
            {
                id: 2,
                name: 'AMD Ryzen 9 7950X',
                brand: 'AMD',
                category: 'cpu',
                price: 2799,
                icon: '⚡',
                image: 'https://images.unsplash.com/photo-1614624532983-4ce03382d63d?w=800&q=80',
                rating: 4.8,
                reviews: 203,
                specs: {
                    'عدد الأنوية': '16 نواة',
                    'عدد الخيوط': '32 خيط',
                    'السرعة الأساسية': '4.5 GHz',
                    'السرعة القصوى': '5.7 GHz',
                    'الذاكرة المخبئية': '64 MB L3',
                    'استهلاك الطاقة': '170W'
                },
                customerReviews: [
                    { name: 'خالد السعيد', date: '2026-01-20', rating: 5, text: 'أقوى معالج استخدمته، مثالي للألعاب والعمل' },
                    { name: 'فهد العتيبي', date: '2026-01-18', rating: 5, text: 'أداء خرافي في البرامج الاحترافية' }
                ]
            },
            {
                id: 3,
                name: 'Corsair Vengeance RGB 32GB',
                brand: 'Corsair',
                category: 'ram',
                price: 699,
                icon: '🧠',
                image: 'https://images.unsplash.com/photo-1625948515291-69613efd103f?w=800&q=80',
                rating: 4.6,
                reviews: 189,
                specs: {
                    'السعة': '32 GB (2x16GB)',
                    'النوع': 'DDR5',
                    'السرعة': '6000 MHz',
                    'التأخير': 'CL36',
                    'الإضاءة': 'RGB',
                    'الجهد': '1.35V'
                },
                customerReviews: [
                    { name: 'عبدالله القحطاني', date: '2026-01-12', rating: 5, text: 'رام رائع، سريع جداً والإضاءة جميلة' },
                    { name: 'محمد الشمري', date: '2026-01-08', rating: 4, text: 'جودة ممتازة وأداء قوي' }
                ]
            },
            {
                id: 4,
                name: 'Samsung 990 PRO 2TB NVMe',
                brand: 'Samsung',
                category: 'storage',
                price: 899,
                icon: '💾',
                image: 'https://images.unsplash.com/photo-1531492746076-161ca9bcad58?w=800&q=80',
                rating: 4.9,
                reviews: 267,
                specs: {
                    'السعة': '2 TB',
                    'النوع': 'M.2 NVMe PCIe 4.0',
                    'سرعة القراءة': '7450 MB/s',
                    'سرعة الكتابة': '6900 MB/s',
                    'الضمان': '5 سنوات',
                    'التحمل': '1200 TBW'
                },
                customerReviews: [
                    { name: 'ياسر الدوسري', date: '2026-01-22', rating: 5, text: 'أسرع هارد استخدمته، يستحق كل ريال' },
                    { name: 'نواف المطيري', date: '2026-01-19', rating: 5, text: 'سرعة خيالية، الويندوز يفتح في ثواني' }
                ]
            },
            {
                id: 5,
                name: 'Intel Core i7-14700K',
                brand: 'Intel',
                category: 'cpu',
                price: 2299,
                icon: '🔥',
                image: 'https://images.unsplash.com/photo-1555617981-dac3880eac6e?w=800&q=80',
                rating: 4.7,
                reviews: 178,
                specs: {
                    'عدد الأنوية': '20 نواة',
                    'عدد الخيوط': '28 خيط',
                    'السرعة الأساسية': '3.4 GHz',
                    'السرعة القصوى': '5.6 GHz',
                    'الذاكرة المخبئية': '33 MB',
                    'استهلاك الطاقة': '125W'
                },
                customerReviews: [
                    { name: 'سلطان الحربي', date: '2026-01-16', rating: 5, text: 'معالج قوي جداً، ينصح به للألعاب' },
                    { name: 'عمر العنزي', date: '2026-01-14', rating: 4, text: 'أداء ممتاز لكن يحتاج تبريد قوي' }
                ]
            },
            {
                id: 6,
                name: 'ASUS ROG STRIX X670E-E',
                brand: 'ASUS',
                category: 'motherboard',
                price: 1899,
                icon: '🔌',
                image: 'https://images.unsplash.com/photo-1587202372775-e229f172b9d7?w=800&q=80',
                rating: 4.8,
                reviews: 145,
                specs: {
                    'المعالج المدعوم': 'AMD Ryzen 7000',
                    'الشريحة': 'AMD X670E',
                    'الذاكرة': 'DDR5 حتى 128GB',
                    'المنافذ': 'PCIe 5.0, USB 3.2 Gen 2x2',
                    'الشبكة': '2.5Gb Ethernet',
                    'الصوت': 'SupremeFX'
                },
                customerReviews: [
                    { name: 'راشد الزهراني', date: '2026-01-21', rating: 5, text: 'لوحة أم احترافية، جودة بناء ممتازة' },
                    { name: 'طلال العتيبي', date: '2026-01-17', rating: 5, text: 'مثالية للبناء الاحترافي' }
                ]
            },
            {
                id: 7,
                name: 'NVIDIA GeForce RTX 4090',
                brand: 'NVIDIA',
                category: 'gpu',
                price: 8999,
                icon: '👑',
                image: 'https://images.unsplash.com/photo-1587202372634-32705e3bf49c?w=800&q=80',
                rating: 5.0,
                reviews: 312,
                specs: {
                    'نوع الذاكرة': 'GDDR6X',
                    'حجم الذاكرة': '24 GB',
                    'سرعة المعالج': '2520 MHz',
                    'استهلاك الطاقة': '450W',
                    'المنافذ': 'HDMI 2.1, DisplayPort 1.4a',
                    'التبريد': 'ثلاث مراوح'
                },
                customerReviews: [
                    { name: 'بندر الغامدي', date: '2026-01-23', rating: 5, text: 'أقوى كرت شاشة في السوق، أداء لا يصدق' },
                    { name: 'ماجد القرني', date: '2026-01-20', rating: 5, text: 'يستحق السعر، جودة استثنائية' }
                ]
            },
            {
                id: 8,
                name: 'NZXT Kraken Z73 RGB',
                brand: 'NZXT',
                category: 'cooling',
                price: 1299,
                icon: '❄️',
                image: 'https://images.unsplash.com/photo-1587202372583-49330a15584d?w=800&q=80',
                rating: 4.7,
                reviews: 198,
                specs: {
                    'النوع': 'تبريد مائي',
                    'حجم المشتت': '360mm',
                    'سرعة المروحة': '500-2000 RPM',
                    'مستوى الضوضاء': '21-36 dB',
                    'الشاشة': 'LCD 2.36 بوصة',
                    'التوافق': 'Intel و AMD'
                },
                customerReviews: [
                    { name: 'فيصل الشهري', date: '2026-01-18', rating: 5, text: 'تبريد ممتاز والشاشة إضافة رائعة' },
                    { name: 'عبدالعزيز السبيعي', date: '2026-01-15', rating: 4, text: 'جودة عالية لكن السعر مرتفع قليلاً' }
                ]
            },
            {
                id: 9,
                name: 'Corsair RM1000x 1000W',
                brand: 'Corsair',
                category: 'psu',
                price: 899,
                icon: '⚙️',
                image: 'https://images.unsplash.com/photo-1587202372616-b43abea06c2a?w=800&q=80',
                rating: 4.9,
                reviews: 223,
                specs: {
                    'القدرة': '1000 واط',
                    'الكفاءة': '80 Plus Gold',
                    'النوع': 'Fully Modular',
                    'المروحة': '135mm',
                    'الضمان': '10 سنوات',
                    'الحماية': 'OVP, UVP, OCP, OTP, SCP'
                },
                customerReviews: [
                    { name: 'عادل المالكي', date: '2026-01-19', rating: 5, text: 'باور موثوق وهادئ جداً' },
                    { name: 'وليد الجهني', date: '2026-01-16', rating: 5, text: 'أفضل استثمار لحماية القطع' }
                ]
            },
            {
                id: 10,
                name: 'G.Skill Trident Z5 64GB',
                brand: 'G.Skill',
                category: 'ram',
                price: 1399,
                icon: '💡',
                image: 'https://images.unsplash.com/photo-1562976540-1502c2145186?w=800&q=80',
                rating: 4.8,
                reviews: 167,
                specs: {
                    'السعة': '64 GB (2x32GB)',
                    'النوع': 'DDR5',
                    'السرعة': '6400 MHz',
                    'التأخير': 'CL32',
                    'الإضاءة': 'RGB',
                    'الجهد': '1.4V'
                },
                customerReviews: [
                    { name: 'تركي الأحمدي', date: '2026-01-17', rating: 5, text: 'رام احترافي للعمل الشاق' },
                    { name: 'حسن العمري', date: '2026-01-13', rating: 5, text: 'سرعة فائقة وموثوقية عالية' }
                ]
            },
            {
                id: 11,
                name: 'WD Black SN850X 4TB',
                brand: 'Western Digital',
                category: 'storage',
                price: 1699,
                icon: '🚀',
                image: 'https://images.unsplash.com/photo-1597872200969-2b65d56bd16b?w=800&q=80',
                rating: 4.7,
                reviews: 189,
                specs: {
                    'السعة': '4 TB',
                    'النوع': 'M.2 NVMe PCIe 4.0',
                    'سرعة القراءة': '7300 MB/s',
                    'سرعة الكتابة': '6600 MB/s',
                    'الضمان': '5 سنوات',
                    'التحمل': '2400 TBW'
                },
                customerReviews: [
                    { name: 'سعود الشهراني', date: '2026-01-14', rating: 5, text: 'مساحة كبيرة وسرعة ممتازة' },
                    { name: 'مشعل الرويلي', date: '2026-01-11', rating: 4, text: 'يستحق السعر للمساحة الكبيرة' }
                ]
            },
            {
                id: 12,
                name: 'AMD Radeon RX 7900 XTX',
                brand: 'AMD',
                category: 'gpu',
                price: 5499,
                icon: '🔴',
                image: 'https://images.unsplash.com/photo-1591488320449-011701bb6704?w=800&q=80',
                rating: 4.6,
                reviews: 234,
                specs: {
                    'نوع الذاكرة': 'GDDR6',
                    'حجم الذاكرة': '24 GB',
                    'سرعة المعالج': '2500 MHz',
                    'استهلاك الطاقة': '355W',
                    'المنافذ': 'HDMI 2.1, DisplayPort 2.1',
                    'التبريد': 'ثلاث مراوح'
                },
                customerReviews: [
                    { name: 'ناصر الحارثي', date: '2026-01-22', rating: 5, text: 'منافس قوي لـ NVIDIA بسعر أفضل' },
                    { name: 'ريان الصالح', date: '2026-01-19', rating: 4, text: 'أداء رائع في الألعاب' }
                ]
            }
        ];

        let cart = [];
        let currentCategory = 'all';
        let searchQuery = '';
        let selectedPayment = null;
        let currentUser = null;
        let verificationCode = null;
        let currentPage = 'home'; // 'home' or 'product' or 'builder'
        let currentProductId = null;
        let isAdminLoggedIn = false;
        const ADMIN_PASSWORD = 'admin123'; // يمكنك تغيير كلمة المرور هنا

        // PC Builder
        let pcBuild = {
            cpu: null,
            gpu: null,
            ram: null,
            storage: null,
            motherboard: null,
            psu: null,
            cooling: null
        };

        // Compatibility rules
        const compatibilityRules = {
            checkCpuMotherboard: (cpu, motherboard) => {
                // AMD Ryzen needs AMD motherboard, Intel needs Intel
                const cpuBrand = cpu.brand.toLowerCase();
                const mbName = motherboard.name.toLowerCase();
                
                if (cpuBrand === 'amd' && mbName.includes('amd')) return { compatible: true };
                if (cpuBrand === 'intel' && mbName.includes('intel')) return { compatible: true };
                
                return { 
                    compatible: false, 
                    message: '⚠️ المعالج واللوحة الأم غير متوافقين. تأكد من اختيار لوحة أم تدعم المعالج.'
                };
            },
            
            checkPowerSupply: (build) => {
                let totalPower = 0;
                if (build.cpu) totalPower += parseInt(build.cpu.specs['استهلاك الطاقة']) || 0;
                if (build.gpu) totalPower += parseInt(build.gpu.specs['استهلاك الطاقة']) || 0;
                
                // Add 150W for other components
                totalPower += 150;
                
                if (build.psu) {
                    const psuPower = parseInt(build.psu.specs['القدرة']);
                    if (psuPower < totalPower) {
                        return {
                            compatible: false,
                            message: `⚠️ مزود الطاقة ضعيف. استهلاك متوقع: ${totalPower}W، المتوفر: ${psuPower}W`
                        };
                    }
                }
                
                return { compatible: true };
            },
            
            checkRamMotherboard: (ram, motherboard) => {
                if (!ram || !motherboard) return { compatible: true };
                
                const ramType = ram.specs['النوع'];
                const mbSupport = motherboard.specs['الذاكرة'];
                
                if (mbSupport && !mbSupport.includes(ramType)) {
                    return {
                        compatible: false,
                        message: `⚠️ اللوحة الأم لا تدعم ${ramType}. تدعم: ${mbSupport}`
                    };
                }
                
                return { compatible: true };
            }
        };

        function checkCompatibility(build) {
            const issues = [];
            
            // Check CPU and Motherboard
            if (build.cpu && build.motherboard) {
                const result = compatibilityRules.checkCpuMotherboard(build.cpu, build.motherboard);
                if (!result.compatible) issues.push(result.message);
            }
            
            // Check RAM and Motherboard
            if (build.ram && build.motherboard) {
                const result = compatibilityRules.checkRamMotherboard(build.ram, build.motherboard);
                if (!result.compatible) issues.push(result.message);
            }
            
            // Check Power Supply
            const psuResult = compatibilityRules.checkPowerSupply(build);
            if (!psuResult.compatible) issues.push(psuResult.message);
            
            return issues;
        }

        let compareList = [];

        function toggleCompare(productId) {
            const product = products.find(p => p.id === productId);
            const index = compareList.findIndex(p => p.id === productId);
            
            if (index > -1) {
                compareList.splice(index, 1);
            } else {
                if (compareList.length >= 3) {
                    showNotification('⚠️ يمكنك مقارنة 3 منتجات كحد أقصى');
                    return;
                }
                compareList.push(product);
            }
            
            updateCompareBar();
        }

        function updateCompareBar() {
            const compareBar = document.getElementById('compareBar');
            const compareItems = document.getElementById('compareItems');
            const compareCount = document.getElementById('compareCount');
            
            if (compareList.length > 0) {
                compareBar.classList.add('active');
                compareItems.innerHTML = compareList.map(p => `
                    <div class="compare-item">
                        <span>${p.name}</span>
                        <button class="compare-item-remove" onclick="toggleCompare(${p.id})">×</button>
                    </div>
                `).join('');
                compareCount.textContent = compareList.length;
            } else {
                compareBar.classList.remove('active');
            }
            
            // Update button states
            document.querySelectorAll('.compare-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            
            compareList.forEach(p => {
                const btn = document.querySelector(`[onclick*="toggleCompare(${p.id})"]`);
                if (btn && btn.classList.contains('compare-btn')) {
                    btn.classList.add('active');
                }
            });
        }

        function clearComparison() {
            compareList = [];
            updateCompareBar();
        }

        function showComparison() {
            if (compareList.length < 2) {
                showNotification('⚠️ اختر منتجين على الأقل للمقارنة');
                return;
            }
            
            // Create comparison table
            let comparisonHTML = `
                <div style="max-width: 1200px; margin: 0 auto; padding: 20px;">
                    <h2 style="color: #2d3436; margin-bottom: 20px;">📊 مقارنة المنتجات</h2>
                    <table style="width: 100%; border-collapse: collapse; background: white;">
                        <thead>
                            <tr style="background: #667eea; color: white;">
                                <th style="padding: 15px; text-align: right; border: 1px solid #ddd;">المواصفات</th>
                                ${compareList.map(p => `<th style="padding: 15px; text-align: center; border: 1px solid #ddd;">${p.name}</th>`).join('')}
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td style="padding: 10px; border: 1px solid #ddd; font-weight: bold;">السعر</td>
                                ${compareList.map(p => `<td style="padding: 10px; border: 1px solid #ddd; text-align: center; color: #667eea; font-weight: bold;">${p.price.toLocaleString()} ريال</td>`).join('')}
                            </tr>
                            <tr>
                                <td style="padding: 10px; border: 1px solid #ddd; font-weight: bold;">التقييم</td>
                                ${compareList.map(p => `<td style="padding: 10px; border: 1px solid #ddd; text-align: center;">${'★'.repeat(Math.floor(p.rating))}${'☆'.repeat(5-Math.floor(p.rating))}</td>`).join('')}
                            </tr>
            `;
            
            // Get all unique spec keys
            const allSpecs = new Set();
            compareList.forEach(p => {
                Object.keys(p.specs).forEach(key => allSpecs.add(key));
            });
            
            allSpecs.forEach(specKey => {
                comparisonHTML += `
                    <tr>
                        <td style="padding: 10px; border: 1px solid #ddd; font-weight: bold;">${specKey}</td>
                        ${compareList.map(p => `<td style="padding: 10px; border: 1px solid #ddd; text-align: center;">${p.specs[specKey] || '-'}</td>`).join('')}
                    </tr>
                `;
            });
            
            comparisonHTML += `
                        </tbody>
                    </table>
                    <div style="margin-top: 20px; text-align: center;">
                        <button onclick="closeComparison()" style="background: #667eea; color: white; border: none; padding: 12px 30px; border-radius: 8px; cursor: pointer; font-weight: bold;">إغلاق</button>
                    </div>
                </div>
            `;
            
            // Show in modal-like div
            const compModal = document.createElement('div');
            compModal.id = 'comparisonModal';
            compModal.style.cssText = 'position: fixed; top: 0; left: 0; right: 0; bottom: 0; background: rgba(0,0,0,0.8); z-index: 10000; overflow-y: auto; padding: 20px;';
            compModal.innerHTML = comparisonHTML;
            document.body.appendChild(compModal);
        }

        function closeComparison() {
            const modal = document.getElementById('comparisonModal');
            if (modal) modal.remove();
        }
        function loadCustomImages() {
            const savedImages = localStorage.getItem('productImages');
            if (savedImages) {
                const images = JSON.parse(savedImages);
                products.forEach(product => {
                    if (images[product.id]) {
                        product.customImages = images[product.id]; // Array of images
                    }
                });
            }
        }

        // Save custom images (multiple)
        function saveProductImages(productId, imageUrl) {
            const savedImages = localStorage.getItem('productImages');
            const allImages = savedImages ? JSON.parse(savedImages) : {};
            
            if (!allImages[productId]) {
                allImages[productId] = [];
            }
            
            // Add new image if not already exists
            if (!allImages[productId].includes(imageUrl)) {
                allImages[productId].push(imageUrl);
            }
            
            localStorage.setItem('productImages', JSON.stringify(allImages));
            
            // Update product object
            const product = products.find(p => p.id === productId);
            if (product) {
                product.customImages = allImages[productId];
            }
            
            showNotification('تم إضافة الصورة بنجاح! ✓');
        }

        // Remove specific image
        function removeSpecificImage(productId, imageUrl) {
            const savedImages = localStorage.getItem('productImages');
            if (savedImages) {
                const allImages = JSON.parse(savedImages);
                if (allImages[productId]) {
                    allImages[productId] = allImages[productId].filter(img => img !== imageUrl);
                    
                    if (allImages[productId].length === 0) {
                        delete allImages[productId];
                    }
                    
                    localStorage.setItem('productImages', JSON.stringify(allImages));
                    
                    // Update product object
                    const product = products.find(p => p.id === productId);
                    if (product) {
                        product.customImages = allImages[productId] || [];
                    }
                    
                    renderAdminPanel();
                    showNotification('تم حذف الصورة بنجاح! ✓');
                }
            }
        }

        // Remove all images for a product
        function removeAllProductImages(productId) {
            const savedImages = localStorage.getItem('productImages');
            if (savedImages) {
                const images = JSON.parse(savedImages);
                delete images[productId];
                localStorage.setItem('productImages', JSON.stringify(images));
                
                // Update product object
                const product = products.find(p => p.id === productId);
                if (product) {
                    product.customImages = [];
                }
                
                renderAdminPanel();
                showNotification('تم حذف جميع الصور بنجاح! ✓');
            }
        }

        // Get product image (custom or placeholder) - returns first image or placeholder
        function getProductImage(product) {
            if (product.customImages && product.customImages.length > 0) {
                return `<img src="${product.customImages[0]}" class="image-preview" onerror="this.style.display='none'" />`;
            } else {
                return `
                    <div class="product-placeholder">
                        <div class="product-placeholder-icon">${product.icon || '📦'}</div>
                        <div class="product-placeholder-text">${product.brand}</div>
                    </div>
                `;
            }
        }

        // Get all product images for gallery
        function getProductGallery(product) {
            if (product.customImages && product.customImages.length > 0) {
                return product.customImages;
            }
            return [];
        }

        // Admin Panel Functions
        function renderAdminPanel() {
            const grid = document.getElementById('adminProductsGrid');
            grid.innerHTML = products.map(product => `
                <div class="admin-product-card">
                    <div class="admin-product-name">${product.name}</div>
                    
                    ${product.customImages && product.customImages.length > 0 ? `
                        <div class="admin-images-list">
                            ${product.customImages.map((img, index) => `
                                <div class="admin-image-item">
                                    <div class="admin-product-image ${product.category}">
                                        <img src="${img}" class="image-preview" />
                                    </div>
                                    <div class="image-controls">
                                        <span class="image-number">صورة ${index + 1}</span>
                                        <button class="remove-single-image-btn" onclick="removeSpecificImage(${product.id}, '${img.replace(/'/g, "\\'")}')">
                                            🗑️ حذف
                                        </button>
                                    </div>
                                </div>
                            `).join('')}
                        </div>
                    ` : `
                        <div class="admin-product-image ${product.category}">
                            ${getProductImage(product)}
                        </div>
                    `}
                    
                    <div class="add-image-section">
                        <input 
                            type="text" 
                            class="image-url-input" 
                            placeholder="رابط صورة جديدة (https://...)" 
                            id="imageUrl${product.id}"
                        />
                        <button class="save-image-btn" onclick="saveImageFromInput(${product.id})">
                            ➕ إضافة صورة
                        </button>
                    </div>
                    
                    ${product.customImages && product.customImages.length > 0 ? `
                        <button class="remove-all-images-btn" onclick="removeAllProductImages(${product.id})">
                            🗑️ حذف جميع الصور (${product.customImages.length})
                        </button>
                    ` : ''}
                </div>
            `).join('');
        }

        function saveImageFromInput(productId) {
            const input = document.getElementById(`imageUrl${productId}`);
            const url = input.value.trim();
            
            if (url && (url.startsWith('http://') || url.startsWith('https://'))) {
                saveProductImages(productId, url);
                input.value = ''; // Clear input after adding
                renderAdminPanel();
                
                // Update current view if needed
                if (currentPage === 'home') {
                    renderProducts();
                } else if (currentPage === 'product' && currentProductId === productId) {
                    renderProductPage(productId);
                }
            } else {
                showNotification('⚠️ يرجى إدخال رابط صحيح');
            }
        }

        // Admin Login
        document.addEventListener('DOMContentLoaded', () => {
            document.getElementById('adminAccessBtn').addEventListener('click', () => {
                document.getElementById('adminPanel').classList.add('active');
            });

            document.getElementById('adminLoginBtn').addEventListener('click', () => {
                const password = document.getElementById('adminPasswordInput').value;
                if (password === ADMIN_PASSWORD) {
                    isAdminLoggedIn = true;
                    document.getElementById('adminLoginScreen').style.display = 'none';
                    document.getElementById('adminDashboard').style.display = 'block';
                    renderAdminPanel();
                    showNotification('تم تسجيل الدخول بنجاح! ✓');
                } else {
                    showNotification('⚠️ كلمة المرور غير صحيحة');
                }
            });

            document.getElementById('closeAdmin').addEventListener('click', () => {
                document.getElementById('adminPanel').classList.remove('active');
            });

            // Allow Enter key to login
            document.getElementById('adminPasswordInput').addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    document.getElementById('adminLoginBtn').click();
                }
            });
        });

        // URL Routing
        function navigateToProduct(productId) {
            currentPage = 'product';
            currentProductId = productId;
            window.history.pushState({ page: 'product', productId }, '', `#product-${productId}`);
            renderProductPage(productId);
        }

        function navigateToHome() {
            currentPage = 'home';
            currentProductId = null;
            window.history.pushState({ page: 'home' }, '', '#');
            renderHomePage();
        }

        function navigateToPCBuilder() {
            currentPage = 'builder';
            window.history.pushState({ page: 'builder' }, '', '#pc-builder');
            renderPCBuilderPage();
        }

        function renderPCBuilderPage() {
            document.getElementById('homePage').style.display = 'none';
            document.getElementById('productPage').style.display = 'none';
            document.getElementById('pcBuilderPage').style.display = 'block';

            const componentTypes = [
                { key: 'cpu', name: 'المعالج (CPU)', category: 'cpu', required: true },
                { key: 'motherboard', name: 'اللوحة الأم', category: 'motherboard', required: true },
                { key: 'ram', name: 'الذاكرة العشوائية (RAM)', category: 'ram', required: true },
                { key: 'storage', name: 'وحدة التخزين', category: 'storage', required: true },
                { key: 'gpu', name: 'كرت الشاشة (GPU)', category: 'gpu', required: false },
                { key: 'psu', name: 'مزود الطاقة', category: 'psu', required: true },
                { key: 'cooling', name: 'نظام التبريد', category: 'cooling', required: false }
            ];

            const componentsList = document.getElementById('builderComponentsList');
            componentsList.innerHTML = componentTypes.map(comp => {
                const categoryProducts = products.filter(p => p.category === comp.category);
                return `
                    <div class="component-selector">
                        <div class="component-header">
                            <div class="component-title">${comp.name}</div>
                            ${comp.required ? '<div class="component-required">مطلوب</div>' : ''}
                        </div>
                        <select class="component-select" onchange="selectComponent('${comp.key}', this.value)">
                            <option value="">-- اختر ${comp.name} --</option>
                            ${categoryProducts.map(p => `
                                <option value="${p.id}">${p.name} - ${p.price.toLocaleString()} ريال</option>
                            `).join('')}
                        </select>
                        <div class="component-info" id="info-${comp.key}"></div>
                    </div>
                `;
            }).join('');

            updateBuilderSummary();
            lucide.createIcons();
        }

        function selectComponent(componentType, productId) {
            if (productId) {
                const product = products.find(p => p.id === parseInt(productId));
                pcBuild[componentType] = product;
                
                // Show component info
                const infoDiv = document.getElementById(`info-${componentType}`);
                if (product) {
                    const mainSpecs = Object.entries(product.specs).slice(0, 3);
                    infoDiv.innerHTML = mainSpecs.map(([key, val]) => `<div><strong>${key}:</strong> ${val}</div>`).join('');
                }
            } else {
                pcBuild[componentType] = null;
                document.getElementById(`info-${componentType}`).innerHTML = '';
            }
            
            updateBuilderSummary();
        }

        function updateBuilderSummary() {
            const summary = document.getElementById('builderSummary');
            const total = document.getElementById('builderTotal');
            const addBtn = document.getElementById('addBuildBtn');
            
            let totalPrice = 0;
            let hasRequired = true;
            
            const summaryItems = [];
            const componentNames = {
                cpu: 'المعالج',
                motherboard: 'اللوحة الأم',
                ram: 'الذاكرة',
                storage: 'التخزين',
                gpu: 'كرت الشاشة',
                psu: 'مزود الطاقة',
                cooling: 'التبريد'
            };
            
            Object.entries(pcBuild).forEach(([key, product]) => {
                if (product) {
                    summaryItems.push(`
                        <div class="summary-item">
                            <div class="summary-label">${componentNames[key]}</div>
                            <div class="summary-value">${product.price.toLocaleString()} ريال</div>
                        </div>
                    `);
                    totalPrice += product.price;
                }
            });
            
            // Check if required components are selected
            if (!pcBuild.cpu || !pcBuild.motherboard || !pcBuild.ram || !pcBuild.storage || !pcBuild.psu) {
                hasRequired = false;
            }
            
            summary.innerHTML = summaryItems.length > 0 ? summaryItems.join('') : '<p style="color: #636e72;">لم تختر أي قطع بعد</p>';
            total.textContent = totalPrice.toLocaleString() + ' ريال';
            
            // Check compatibility
            const issues = checkCompatibility(pcBuild);
            const compatDiv = document.getElementById('compatibilityCheck');
            const issuesDiv = document.getElementById('compatibilityIssues');
            
            if (issues.length > 0) {
                compatDiv.style.display = 'block';
                issuesDiv.innerHTML = issues.map(issue => `<div class="compatibility-issue">${issue}</div>`).join('');
            } else {
                compatDiv.style.display = 'none';
            }
            
            addBtn.disabled = !hasRequired || issues.length > 0;
        }

        function addBuildToCart() {
            Object.values(pcBuild).forEach(product => {
                if (product) {
                    addToCart(product.id);
                }
            });
            
            showNotification('تم إضافة جميع القطع للسلة! ✓');
            document.getElementById('cartModal').classList.add('active');
        }

        function showBuyingGuide() {
            alert(`📖 دليل الشراء الشامل

🎯 للألعاب:
- معالج: Intel i7 أو AMD Ryzen 7
- كرت شاشة: RTX 4060 أو أعلى
- رام: 16-32 GB DDR5
- تخزين: SSD NVMe 1TB

💼 للعمل والإنتاجية:
- معالج: Intel i5 أو AMD Ryzen 5
- كرت شاشة: مدمج أو RTX 4060
- رام: 16 GB DDR5
- تخزين: SSD NVMe 512GB

💡 نصائح مهمة:
- تأكد من توافق المعالج مع اللوحة الأم
- احسب استهلاك الطاقة واختر مزود طاقة مناسب
- استخدم أداة بناء الكمبيوتر للتحقق من التوافق`);
        }

        // Handle browser back/forward buttons
        window.addEventListener('popstate', (event) => {
            if (event.state) {
                if (event.state.page === 'product') {
                    currentPage = 'product';
                    currentProductId = event.state.productId;
                    renderProductPage(event.state.productId);
                } else {
                    currentPage = 'home';
                    currentProductId = null;
                    renderHomePage();
                }
            } else {
                navigateToHome();
            }
        });

        // Check URL on page load
        window.addEventListener('load', () => {
            const hash = window.location.hash;
            if (hash.startsWith('#product-')) {
                const productId = parseInt(hash.replace('#product-', ''));
                navigateToProduct(productId);
            } else {
                window.history.replaceState({ page: 'home' }, '', '#');
            }
        });

        function renderHomePage() {
            document.getElementById('homePage').style.display = 'block';
            document.getElementById('productPage').style.display = 'none';
            renderProducts();
        }

        function renderProductPage(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) {
                navigateToHome();
                return;
            }

            document.getElementById('homePage').style.display = 'none';
            document.getElementById('productPage').style.display = 'block';

            const productPageContent = document.getElementById('productPageContent');
            const gallery = getProductGallery(product);
            const hasGallery = gallery.length > 0;

            productPageContent.innerHTML = `
                <div class="product-page-header">
                    <button class="back-btn" onclick="navigateToHome()">
                        <i data-lucide="arrow-right"></i>
                        <span>العودة للمتجر</span>
                    </button>
                    <div class="breadcrumb">
                        <span onclick="navigateToHome()" style="cursor: pointer; color: #667eea;">الرئيسية</span>
                        <span style="margin: 0 10px;">/</span>
                        <span>${product.name}</span>
                    </div>
                </div>

                <div class="product-page-grid">
                    <div class="product-gallery-container">
                        <div class="main-product-image ${product.category}" id="mainProductImage">
                            ${hasGallery ? `<img src="${gallery[0]}" class="image-preview" />` : getProductImage(product)}
                        </div>
                        
                        ${hasGallery && gallery.length > 1 ? `
                            <div class="gallery-thumbnails">
                                ${gallery.map((img, index) => `
                                    <div class="gallery-thumbnail ${product.category} ${index === 0 ? 'active' : ''}" 
                                         onclick="changeMainImage(${product.id}, ${index})"
                                         id="thumbnail${index}">
                                        <img src="${img}" />
                                    </div>
                                `).join('')}
                            </div>
                        ` : ''}
                    </div>

                    <div class="product-page-info">
                        <div class="product-brand">${product.brand}</div>
                        <h1 class="product-page-title">${product.name}</h1>
                        
                        <div class="product-rating">
                            <span class="stars">${'★'.repeat(Math.floor(product.rating))}${'☆'.repeat(5-Math.floor(product.rating))}</span>
                            <span class="rating-count">(${product.reviews} تقييم)</span>
                        </div>

                        <div class="product-page-price">${product.price.toLocaleString()} ريال</div>

                        <div class="product-actions">
                            <button class="add-to-cart-btn-large" onclick="addToCart(${product.id})">
                                <i data-lucide="shopping-cart"></i>
                                <span>أضف للسلة</span>
                            </button>
                            <button class="buy-now-btn" onclick="buyNow(${product.id})">
                                <i data-lucide="zap"></i>
                                <span>اشتر الآن</span>
                            </button>
                        </div>

                        <div class="specs-section">
                            <h3>المواصفات التقنية</h3>
                            ${Object.entries(product.specs).map(([key, value]) => `
                                <div class="spec-item">
                                    <div class="spec-label">${key}:</div>
                                    <div class="spec-value">${value}</div>
                                </div>
                            `).join('')}
                        </div>
                    </div>
                </div>

                <div class="reviews-section">
                    <h3>آراء العملاء (${product.reviews})</h3>
                    <div class="reviews-grid">
                        ${product.customerReviews.map(review => `
                            <div class="review-item">
                                <div class="review-header">
                                    <div class="reviewer-name">${review.name}</div>
                                    <div class="review-date">${review.date}</div>
                                </div>
                                <div class="review-stars">${'★'.repeat(review.rating)}${'☆'.repeat(5-review.rating)}</div>
                                <div class="review-text">${review.text}</div>
                            </div>
                        `).join('')}
                    </div>
                </div>

                <div class="related-products">
                    <h3>منتجات مشابهة</h3>
                    <div class="related-products-grid">
                        ${products
                            .filter(p => p.category === product.category && p.id !== product.id)
                            .slice(0, 4)
                            .map(p => `
                                <div class="product-card-small" onclick="navigateToProduct(${p.id})">
                                    <div class="product-image-small ${p.category}">
                                        ${getProductImage(p)}
                                    </div>
                                    <div class="product-name-small">${p.name}</div>
                                    <div class="product-price-small">${p.price.toLocaleString()} ريال</div>
                                </div>
                            `).join('')}
                    </div>
                </div>
            `;

            lucide.createIcons();
            window.scrollTo(0, 0);
        }

        function buyNow(productId) {
            addToCart(productId);
            document.getElementById('cartModal').classList.add('active');
        }

        function changeMainImage(productId, imageIndex) {
            const product = products.find(p => p.id === productId);
            if (!product || !product.customImages || !product.customImages[imageIndex]) return;

            // Update main image
            const mainImage = document.getElementById('mainProductImage');
            mainImage.innerHTML = `<img src="${product.customImages[imageIndex]}" class="image-preview" />`;

            // Update active thumbnail
            const thumbnails = document.querySelectorAll('.gallery-thumbnail');
            thumbnails.forEach((thumb, index) => {
                if (index === imageIndex) {
                    thumb.classList.add('active');
                } else {
                    thumb.classList.remove('active');
                }
            });
        }
        function renderProducts() {
            const grid = document.getElementById('productsGrid');
            const filtered = products.filter(p => {
                const matchesCategory = currentCategory === 'all' || p.category === currentCategory;
                const matchesSearch = p.name.toLowerCase().includes(searchQuery.toLowerCase()) || 
                                    p.brand.toLowerCase().includes(searchQuery.toLowerCase());
                return matchesCategory && matchesSearch;
            });

            grid.innerHTML = filtered.map(product => `
                <div class="product-card" onclick="navigateToProduct(${product.id})">
                    <div class="product-image ${product.category}">
                        ${getProductImage(product)}
                    </div>
                    <div class="product-info">
                        <div class="product-brand">${product.brand}</div>
                        <div class="product-name">${product.name}</div>
                        <div class="product-rating">
                            <span class="stars">${'★'.repeat(Math.floor(product.rating))}${'☆'.repeat(5-Math.floor(product.rating))}</span>
                            <span class="rating-count">(${product.reviews})</span>
                        </div>
                        <div class="product-price">${product.price.toLocaleString()} ريال</div>
                        <div class="product-card-actions">
                            <button class="add-to-cart-btn" onclick="event.stopPropagation(); addToCart(${product.id})">
                                <i data-lucide="shopping-cart"></i>
                                <span>أضف للسلة</span>
                            </button>
                            <button class="compare-btn" onclick="event.stopPropagation(); toggleCompare(${product.id})" title="قارن">
                                <i data-lucide="git-compare"></i>
                            </button>
                        </div>
                    </div>
                </div>
            `).join('');

            lucide.createIcons();
        }

        function showProductDetail(productId) {
            const product = products.find(p => p.id === productId);
            const modal = document.getElementById('productModal');
            const detail = document.getElementById('productDetail');

            detail.innerHTML = `
                <div class="product-detail-grid">
                    <div class="product-detail-image ${product.category}">
                        <div class="product-placeholder">
                            <div class="product-placeholder-icon" style="font-size: 120px;">${product.icon || '📦'}</div>
                            <div class="product-placeholder-text" style="font-size: 18px;">${product.brand}</div>
                        </div>
                    </div>
                    <div class="product-detail-info">
                        <div class="product-brand">${product.brand}</div>
                        <h2>${product.name}</h2>
                        <div class="product-rating">
                            <span class="stars">${'★'.repeat(Math.floor(product.rating))}${'☆'.repeat(5-Math.floor(product.rating))}</span>
                            <span class="rating-count">(${product.reviews} تقييم)</span>
                        </div>
                        <div class="product-detail-price">${product.price.toLocaleString()} ريال</div>
                        
                        <div class="specs-section">
                            <h3>المواصفات التقنية</h3>
                            ${Object.entries(product.specs).map(([key, value]) => `
                                <div class="spec-item">
                                    <div class="spec-label">${key}:</div>
                                    <div class="spec-value">${value}</div>
                                </div>
                            `).join('')}
                        </div>
                        
                        <button class="add-to-cart-btn" onclick="addToCart(${product.id}); closeProductModal()">
                            <i data-lucide="shopping-cart"></i>
                            <span>أضف للسلة</span>
                        </button>
                    </div>
                </div>
                
                <div class="reviews-section">
                    <h3>آراء العملاء</h3>
                    ${product.customerReviews.map(review => `
                        <div class="review-item">
                            <div class="review-header">
                                <div class="reviewer-name">${review.name}</div>
                                <div class="review-date">${review.date}</div>
                            </div>
                            <div class="review-stars">${'★'.repeat(review.rating)}${'☆'.repeat(5-review.rating)}</div>
                            <div class="review-text">${review.text}</div>
                        </div>
                    `).join('')}
                </div>
            `;

            modal.classList.add('active');
            lucide.createIcons();
        }

        function closeProductModal() {
            document.getElementById('productModal').classList.remove('active');
        }

        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            const existingItem = cart.find(item => item.id === productId);

            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({ ...product, quantity: 1 });
            }

            updateCart();
            showNotification('تمت الإضافة للسلة ✓');
        }

        function updateCart() {
            const cartCount = document.getElementById('cartCount');
            const cartItems = document.getElementById('cartItems');
            const cartTotal = document.getElementById('cartTotal');
            const totalAmount = document.getElementById('totalAmount');
            const checkoutBtn = document.getElementById('checkoutBtn');
            const paymentSection = document.getElementById('paymentSection');

            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCount.textContent = totalItems;

            if (cart.length === 0) {
                cartItems.innerHTML = `
                    <div class="empty-cart">
                        <div style="font-size: 80px; opacity: 0.3;">🛒</div>
                        <p>السلة فارغة</p>
                    </div>
                `;
                cartTotal.style.display = 'none';
                checkoutBtn.style.display = 'none';
                paymentSection.style.display = 'none';
            } else {
                cartItems.innerHTML = cart.map(item => `
                    <div class="cart-item">
                        <div class="cart-item-image ${item.category}">
                            ${item.customImages && item.customImages.length > 0 ? `<img src="${item.customImages[0]}" class="image-preview" />` : `<div style="font-size: 32px;">${item.icon || '📦'}</div>`}
                        </div>
                        <div class="cart-item-details">
                            <div class="cart-item-name">${item.name}</div>
                            <div class="cart-item-price">${item.price.toLocaleString()} ريال</div>
                        </div>
                        <div class="cart-item-controls">
                            <button class="qty-btn" onclick="decreaseQuantity(${item.id})">-</button>
                            <div class="qty-display">${item.quantity}</div>
                            <button class="qty-btn" onclick="increaseQuantity(${item.id})">+</button>
                            <button class="remove-btn" onclick="removeFromCart(${item.id})">حذف</button>
                        </div>
                    </div>
                `).join('');

                const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
                totalAmount.textContent = total.toLocaleString();
                cartTotal.style.display = 'block';
                checkoutBtn.style.display = 'block';
                paymentSection.style.display = 'block';
            }

            lucide.createIcons();
        }

        function increaseQuantity(productId) {
            const item = cart.find(i => i.id === productId);
            if (item) {
                item.quantity++;
                updateCart();
            }
        }

        function decreaseQuantity(productId) {
            const item = cart.find(i => i.id === productId);
            if (item && item.quantity > 1) {
                item.quantity--;
                updateCart();
            }
        }

        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            updateCart();
        }

        function showNotification(message) {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            notification.classList.add('show');
            setTimeout(() => {
                notification.classList.remove('show');
            }, 2000);
        }

        // Login functionality
        let isVerificationSent = false;

        document.getElementById('loginBtn').addEventListener('click', () => {
            const email = document.getElementById('emailInput').value;
            const codeInput = document.getElementById('codeInput').value;

            if (!isVerificationSent) {
                if (!email || !email.includes('@')) {
                    showNotification('يرجى إدخال بريد إلكتروني صحيح');
                    return;
                }

                // Generate verification code
                verificationCode = Math.floor(100000 + Math.random() * 900000).toString();
                document.getElementById('verificationCode').textContent = verificationCode;
                document.getElementById('verificationSection').style.display = 'block';
                document.getElementById('loginBtn').textContent = 'تحقق من الكود';
                isVerificationSent = true;
                showNotification('تم إرسال كود التحقق!');
            } else {
                if (codeInput === verificationCode) {
                    currentUser = email;
                    document.getElementById('userBtnText').textContent = email.split('@')[0];
                    document.getElementById('loginModal').classList.remove('active');
                    showNotification('تم تسجيل الدخول بنجاح ✓');
                    
                    // Reset form
                    document.getElementById('emailInput').value = '';
                    document.getElementById('codeInput').value = '';
                    document.getElementById('verificationSection').style.display = 'none';
                    document.getElementById('loginBtn').textContent = 'إرسال كود التحقق';
                    isVerificationSent = false;
                } else {
                    showNotification('كود التحقق غير صحيح');
                }
            }
        });

        // Payment method selection
        document.querySelectorAll('.payment-method').forEach(method => {
            method.addEventListener('click', () => {
                document.querySelectorAll('.payment-method').forEach(m => m.classList.remove('selected'));
                method.classList.add('selected');
                selectedPayment = method.dataset.payment;
            });
        });

        // Event Listeners
        document.querySelectorAll('.category-btn').forEach(btn => {
            btn.addEventListener('click', () => {
                document.querySelectorAll('.category-btn').forEach(b => b.classList.remove('active'));
                btn.classList.add('active');
                currentCategory = btn.dataset.category;
                renderProducts();
            });
        });

        document.getElementById('searchInput').addEventListener('input', (e) => {
            searchQuery = e.target.value;
            renderProducts();
        });

        document.getElementById('userBtn').addEventListener('click', () => {
            if (!currentUser) {
                document.getElementById('loginModal').classList.add('active');
            }
        });

        document.getElementById('cartBtn').addEventListener('click', () => {
            document.getElementById('cartModal').classList.add('active');
        });

        document.getElementById('closeProduct').addEventListener('click', closeProductModal);
        document.getElementById('closeLogin').addEventListener('click', () => {
            document.getElementById('loginModal').classList.remove('active');
        });
        document.getElementById('closeCart').addEventListener('click', () => {
            document.getElementById('cartModal').classList.remove('active');
        });

        document.getElementById('checkoutBtn').addEventListener('click', () => {
            if (!currentUser) {
                showNotification('يرجى تسجيل الدخول أولاً');
                document.getElementById('cartModal').classList.remove('active');
                document.getElementById('loginModal').classList.add('active');
                return;
            }

            if (!selectedPayment) {
                showNotification('يرجى اختيار طريقة الدفع');
                return;
            }

            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const paymentName = selectedPayment === 'visa' ? 'Visa' : selectedPayment === 'mastercard' ? 'MasterCard' : 'مدى';
            
            alert(`شكراً لطلبك! 🎉\n\nالمبلغ الإجمالي: ${total.toLocaleString()} ريال\nطريقة الدفع: ${paymentName}\n\nسيتم التواصل معك على: ${currentUser}\nلإتمام عملية الدفع والتوصيل.`);
            
            cart = [];
            selectedPayment = null;
            updateCart();
            document.getElementById('cartModal').classList.remove('active');
            document.querySelectorAll('.payment-method').forEach(m => m.classList.remove('selected'));
        });

        // Initialize
        loadCustomImages();
        renderHomePage();
        lucide.createIcons();
    </script>
</body>
</html>
