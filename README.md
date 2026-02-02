<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
    <meta name="mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="theme-color" content="#1a5f3f">
    <meta name="description" content="متجر متخصص في بيع قطع الحاسب الآلي عالية الجودة مع محتوى تعليمي شامل">
    <title>متجر قطع الحاسب الآلي - PC Hardware Store</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;800&family=Tajawal:wght@400;500;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --kku-green: #1a5f3f;
            --kku-gold: #c9962b;
            --kku-dark-green: #0d4029;
            --kku-light-green: #2d7a54;
            --white: #ffffff;
            --light-gray: #f5f5f5;
            --gray: #666666;
            --dark: #1a1a1a;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Cairo', 'Tajawal', sans-serif;
            background: linear-gradient(135deg, #f5f5f5 0%, #e8e8e8 100%);
            color: var(--dark);
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, var(--kku-dark-green) 0%, var(--kku-green) 100%);
            box-shadow: 0 4px 20px rgba(26, 95, 63, 0.3);
            position: sticky;
            top: 0;
            z-index: 1000;
            animation: slideDown 0.5s ease-out;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-100%);
            }
            to {
                transform: translateY(0);
            }
        }

        .header-top {
            background: var(--kku-dark-green);
            padding: 12px 0;
            border-bottom: 2px solid var(--kku-gold);
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 15px;
        }

        .header-top .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 10px;
        }

        .logo-section {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .logo {
            width: 50px;
            height: 50px;
            background: var(--white);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            font-weight: 800;
            color: var(--kku-green);
            border: 3px solid var(--kku-gold);
            box-shadow: 0 4px 12px rgba(201, 150, 43, 0.4);
            transition: transform 0.3s ease;
            flex-shrink: 0;
        }

        .logo:hover {
            transform: rotate(360deg) scale(1.1);
        }

        .brand-text h1 {
            font-family: 'Tajawal', sans-serif;
            color: var(--kku-gold);
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 2px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .brand-text p {
            color: var(--white);
            font-size: 11px;
            font-weight: 300;
            letter-spacing: 0.5px;
        }

        .header-actions {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
        }

        .action-btn {
            background: transparent;
            border: 2px solid var(--kku-gold);
            color: var(--white);
            padding: 8px 16px;
            border-radius: 25px;
            cursor: pointer;
            font-family: 'Cairo', sans-serif;
            font-size: 13px;
            font-weight: 600;
            transition: all 0.3s ease;
            white-space: nowrap;
            min-height: 44px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .action-btn:hover,
        .action-btn:active {
            background: var(--kku-gold);
            color: var(--kku-dark-green);
            transform: translateY(-2px);
        }

        /* Navigation */
        nav {
            background: var(--kku-green);
            padding: 0;
        }

        .menu-toggle {
            display: none;
            background: transparent;
            border: 2px solid var(--kku-gold);
            color: var(--white);
            padding: 12px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 18px;
            margin: 10px auto;
            width: calc(100% - 30px);
            max-width: 300px;
            min-height: 48px;
            font-weight: bold;
        }

        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 5px;
            padding: 12px 0;
        }

        nav ul li a {
            color: var(--white);
            text-decoration: none;
            font-size: 15px;
            font-weight: 600;
            padding: 10px 16px;
            border-radius: 8px;
            transition: all 0.3s ease;
            display: block;
            min-height: 44px;
            display: flex;
            align-items: center;
        }

        nav ul li a:hover,
        nav ul li a:active {
            background: rgba(255, 255, 255, 0.15);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--kku-green) 0%, var(--kku-light-green) 100%);
            padding: 40px 15px;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -10%;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(201, 150, 43, 0.15) 0%, transparent 70%);
            animation: pulse 4s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% {
                transform: scale(1);
                opacity: 0.5;
            }
            50% {
                transform: scale(1.2);
                opacity: 0.8;
            }
        }

        .hero-content {
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
            position: relative;
            z-index: 1;
        }

        .hero h2 {
            font-family: 'Tajawal', sans-serif;
            font-size: 32px;
            color: var(--white);
            margin-bottom: 16px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            font-weight: 700;
            line-height: 1.4;
        }

        .hero p {
            font-size: 16px;
            color: var(--white);
            margin-bottom: 24px;
            line-height: 1.8;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero-btn {
            background: var(--kku-gold);
            color: var(--white);
            padding: 14px 32px;
            border: none;
            border-radius: 30px;
            font-size: 16px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 6px 20px rgba(201, 150, 43, 0.4);
            min-height: 48px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
        }

        .hero-btn:hover,
        .hero-btn:active {
            background: var(--white);
            color: var(--kku-green);
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(201, 150, 43, 0.6);
        }

        /* Section Title */
        .section {
            padding: 40px 15px;
        }

        .section-title {
            text-align: center;
            margin-bottom: 35px;
        }

        .section-title h2 {
            font-family: 'Tajawal', sans-serif;
            font-size: 28px;
            color: var(--kku-green);
            margin-bottom: 12px;
            position: relative;
            display: inline-block;
            font-weight: 700;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 4px;
            background: var(--kku-gold);
        }

        .section-title p {
            font-size: 15px;
            color: var(--gray);
            max-width: 700px;
            margin: 15px auto 0;
            line-height: 1.8;
        }

        /* Grid Layouts */
        .grid-3 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            max-width: 1400px;
            margin: 0 auto;
        }

        /* Feature Card */
        .feature-card {
            background: var(--white);
            padding: 25px 20px;
            border-radius: 15px;
            box-shadow: 0 6px 25px rgba(0, 0, 0, 0.08);
            transition: all 0.3s ease;
            border-top: 4px solid var(--kku-gold);
            text-align: center;
        }

        .feature-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 35px rgba(26, 95, 63, 0.15);
        }

        .feature-icon {
            font-size: 42px;
            margin-bottom: 16px;
            display: block;
        }

        .feature-card h3 {
            font-size: 19px;
            color: var(--kku-green);
            margin-bottom: 12px;
            font-weight: 700;
        }

        .feature-card p {
            font-size: 14px;
            color: var(--gray);
            line-height: 1.7;
        }

        /* Product Card */
        .product-card {
            background: var(--white);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 6px 25px rgba(0, 0, 0, 0.08);
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
        }

        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 35px rgba(26, 95, 63, 0.15);
        }

        .product-image {
            height: 200px;
            background: var(--white);
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            padding: 20px;
            border-bottom: 2px solid var(--light-gray);
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: contain;
        }

        .product-info {
            padding: 20px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .product-category {
            color: var(--kku-gold);
            font-size: 11px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 6px;
        }

        .product-name {
            font-size: 18px;
            color: var(--kku-green);
            margin-bottom: 10px;
            font-weight: 700;
        }

        .product-description {
            font-size: 13px;
            color: var(--gray);
            line-height: 1.6;
            margin-bottom: 16px;
            flex-grow: 1;
        }

        .product-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 12px;
            margin-top: auto;
            padding-top: 12px;
            border-top: 2px solid var(--light-gray);
        }

        .product-price {
            font-size: 20px;
            color: var(--kku-green);
            font-weight: 800;
        }

        .product-btn {
            background: var(--kku-gold);
            color: var(--white);
            padding: 10px 20px;
            border: none;
            border-radius: 25px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 13px;
            white-space: nowrap;
            min-height: 44px;
            font-family: 'Cairo', sans-serif;
        }

        .product-btn:hover,
        .product-btn:active {
            background: var(--kku-green);
            transform: scale(1.05);
        }

        .product-btn:disabled {
            opacity: 0.7;
            cursor: not-allowed;
        }

        /* Use Case Card */
        .use-case-card {
            background: var(--white);
            padding: 25px 20px;
            border-radius: 20px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            border-right: 5px solid var(--kku-gold);
        }

        .use-case-card:hover {
            transform: translateX(-5px);
            box-shadow: 0 12px 40px rgba(26, 95, 63, 0.15);
        }

        .use-case-icon {
            font-size: 48px;
            display: block;
            margin-bottom: 16px;
        }

        .use-case-title {
            font-size: 20px;
            color: var(--kku-green);
            margin-bottom: 12px;
            font-weight: 700;
        }

        .use-case-description {
            font-size: 14px;
            color: var(--gray);
            margin-bottom: 16px;
            line-height: 1.7;
        }

        .specs-list {
            list-style: none;
            padding: 0;
        }

        .specs-list li {
            padding: 8px 0;
            border-bottom: 1px solid var(--light-gray);
            font-size: 13px;
            color: var(--dark);
        }

        .specs-list li:last-child {
            border-bottom: none;
            font-weight: 700;
            color: var(--kku-green);
            margin-top: 8px;
        }

        /* Footer */
        footer {
            background: linear-gradient(135deg, var(--kku-dark-green) 0%, var(--kku-green) 100%);
            color: var(--white);
            padding: 40px 15px 20px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 25px;
            margin-bottom: 25px;
        }

        .footer-section h3 {
            color: var(--kku-gold);
            margin-bottom: 12px;
            font-size: 18px;
            font-weight: 700;
        }

        .footer-section p {
            font-size: 14px;
            line-height: 1.7;
            color: rgba(255, 255, 255, 0.9);
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 8px;
        }

        .footer-section ul li a {
            color: rgba(255, 255, 255, 0.9);
            text-decoration: none;
            font-size: 14px;
            transition: color 0.3s ease;
        }

        .footer-section ul li a:hover {
            color: var(--kku-gold);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
            font-size: 13px;
        }

        /* Mobile Responsive */
        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }

            nav ul {
                flex-direction: column;
                padding: 0;
                display: none;
            }

            nav ul.show {
                display: flex;
            }

            nav ul li {
                width: 100%;
                text-align: center;
                border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            }

            nav ul li a {
                justify-content: center;
                padding: 15px;
            }

            .hero {
                padding: 30px 15px;
            }

            .hero h2 {
                font-size: 24px;
            }

            .hero p {
                font-size: 14px;
            }

            .hero-btn {
                width: 100%;
                max-width: 280px;
                padding: 12px 24px;
                font-size: 15px;
            }

            .section {
                padding: 30px 15px;
            }

            .section-title h2 {
                font-size: 22px;
            }

            .section-title p {
                font-size: 14px;
            }

            .grid-3 {
                grid-template-columns: 1fr;
                gap: 15px;
            }

            .feature-card {
                padding: 20px 15px;
            }

            .feature-icon {
                font-size: 36px;
                margin-bottom: 12px;
            }

            .feature-card h3 {
                font-size: 17px;
            }

            .feature-card p {
                font-size: 13px;
            }

            .product-image {
                height: 160px;
                padding: 15px;
            }

            .product-info {
                padding: 15px;
            }

            .product-name {
                font-size: 16px;
            }

            .product-description {
                font-size: 12px;
            }

            .product-footer {
                flex-direction: column;
                gap: 10px;
            }

            .product-btn {
                width: 100%;
            }

            .product-price {
                text-align: center;
                font-size: 18px;
            }

            .use-case-card {
                border-right: none;
                border-top: 5px solid var(--kku-gold);
                padding: 20px 15px;
            }

            .use-case-icon {
                font-size: 40px;
                margin-bottom: 12px;
            }

            .use-case-title {
                font-size: 18px;
            }

            .use-case-description {
                font-size: 13px;
            }

            .specs-list li {
                font-size: 12px;
                padding: 6px 0;
            }

            .footer-content {
                grid-template-columns: 1fr;
                gap: 20px;
            }

            .footer-section h3 {
                font-size: 16px;
            }

            .footer-section p,
            .footer-section ul li,
            .footer-section ul li a {
                font-size: 13px;
            }
        }

        @media (max-width: 480px) {
            .logo {
                width: 45px;
                height: 45px;
                font-size: 22px;
            }

            .brand-text h1 {
                font-size: 16px;
            }

            .brand-text p {
                font-size: 10px;
            }

            .action-btn {
                font-size: 12px;
                padding: 6px 12px;
            }

            .hero h2 {
                font-size: 20px;
            }

            .hero p {
                font-size: 13px;
            }

            .section-title h2 {
                font-size: 20px;
            }

            .feature-icon,
            .use-case-icon {
                font-size: 32px;
            }

            .product-image {
                height: 140px;
            }
        }

        /* Loading Animation */
        .fade-in {
            animation: fadeIn 0.6s ease-in;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-top">
            <div class="container">
                <div class="logo-section">
                    <div class="logo">PC</div>
                    <div class="brand-text">
                        <h1>متجر قطع الحاسب الآلي</h1>
                        <p>التميز في التقنية والجودة</p>
                    </div>
                </div>
                <div class="header-actions">
                    <button class="action-btn">تسجيل الدخول</button>
                    <button class="action-btn">السلة (<span id="cart-count">0</span>)</button>
                </div>
            </div>
        </div>
        <nav>
            <div class="container">
                <button class="menu-toggle" id="menuToggle">القائمة ☰</button>
                <ul id="navMenu">
                    <li><a href="#home">الرئيسية</a></li>
                    <li><a href="#products">المنتجات</a></li>
                    <li><a href="#features">المميزات</a></li>
                    <li><a href="#use-cases">حالات الاستخدام</a></li>
                    <li><a href="#contact">اتصل بنا</a></li>
                </ul>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h2>وجهتك الأولى لقطع الحاسب عالية الجودة</h2>
            <p>نوفر لك أفضل قطع الهاردوير مع محتوى تعليمي شامل يساعدك على اختيار ما يناسب احتياجاتك وميزانيتك</p>
            <button class="hero-btn" onclick="scrollToSection('products')">استكشف المنتجات</button>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="section">
        <div class="container">
            <div class="section-title">
                <h2>لماذا نحن الخيار الأمثل؟</h2>
                <p>نقدم تجربة تسوق فريدة تجمع بين الجودة والمعرفة والشفافية</p>
            </div>
            <div class="grid-3">
                <div class="feature-card fade-in">
                    <span class="feature-icon">🎓</span>
                    <h3>محتوى تعليمي شامل</h3>
                    <p>شروحات تفصيلية لكل قطعة مع أمثلة واقعية وإرشادات واضحة تساعدك على فهم مكونات الحاسب</p>
                </div>
                <div class="feature-card fade-in">
                    <span class="feature-icon">⚙️</span>
                    <h3>فحص التوافق التلقائي</h3>
                    <p>نظام ذكي يتحقق من توافق القطع مع بعضها البعض ويحذرك من أي مشكلة قبل الشراء</p>
                </div>
                <div class="feature-card fade-in">
                    <span class="feature-icon">💡</span>
                    <h3>اقتراحات مخصصة</h3>
                    <p>تجميعات جاهزة حسب نوع الاستخدام والميزانية للألعاب والتصميم والاستخدام المكتبي</p>
                </div>
                <div class="feature-card fade-in">
                    <span class="feature-icon">🔍</span>
                    <h3>مقارنات تقنية</h3>
                    <p>قارن بين المنتجات المختلفة بناءً على المواصفات والأداء والأسعار</p>
                </div>
                <div class="feature-card fade-in">
                    <span class="feature-icon">✅</span>
                    <h3>جودة مضمونة</h3>
                    <p>جميع المنتجات أصلية مع ضمان رسمي وخدمة ما بعد البيع الممتازة</p>
                </div>
                <div class="feature-card fade-in">
                    <span class="feature-icon">🚚</span>
                    <h3>شحن سريع وآمن</h3>
                    <p>توصيل سريع لجميع مناطق المملكة مع تغليف احترافي يضمن السلامة</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="section" style="background: var(--light-gray);">
        <div class="container">
            <div class="section-title">
                <h2>أحدث المنتجات</h2>
                <p>تشكيلة واسعة من قطع الحاسب عالية الجودة</p>
            </div>
            <div class="grid-3">
                <div class="product-card fade-in">
                    <div class="product-image">
                        <img src="intel-i7.png" alt="Intel Core i7-14700K">
                    </div>
                    <div class="product-info">
                        <div class="product-category">معالجات</div>
                        <h3 class="product-name">Intel Core i7-14700K</h3>
                        <p class="product-description">معالج قوي بـ 20 نواة و28 خيط، مثالي للألعاب والتصميم</p>
                        <div class="product-footer">
                            <span class="product-price">1,899 ريال</span>
                            <button class="product-btn" onclick="addToCart(this)">أضف للسلة</button>
                        </div>
                    </div>
                </div>

                <div class="product-card fade-in">
                    <div class="product-image">
                        <img src="rtx-4070.png" alt="NVIDIA RTX 4070 Ti">
                    </div>
                    <div class="product-info">
                        <div class="product-category">كروت الشاشة</div>
                        <h3 class="product-name">NVIDIA RTX 4070 Ti</h3>
                        <p class="product-description">كرت شاشة احترافي بذاكرة 12GB لتجربة ألعاب استثنائية</p>
                        <div class="product-footer">
                            <span class="product-price">3,499 ريال</span>
                            <button class="product-btn" onclick="addToCart(this)">أضف للسلة</button>
                        </div>
                    </div>
                </div>

                <div class="product-card fade-in">
                    <div class="product-image">
                        <img src="asus-motherboard.png" alt="ASUS ROG MAXIMUS Z790 HERO">
                    </div>
                    <div class="product-info">
                        <div class="product-category">اللوحات الأم</div>
                        <h3 class="product-name">ASUS ROG MAXIMUS Z790 HERO</h3>
                        <p class="product-description">لوحة أم متطورة بدعم DDR5 و PCIe 5.0 متقدم</p>
                        <div class="product-footer">
                            <span class="product-price">1,299 ريال</span>
                            <button class="product-btn" onclick="addToCart(this)">أضف للسلة</button>
                        </div>
                    </div>
                </div>

                <div class="product-card fade-in">
                    <div class="product-image">
                        <img src="corsair-ram.png" alt="Corsair Vengeance RGB 32GB">
                    </div>
                    <div class="product-info">
                        <div class="product-category">ذاكرة عشوائية</div>
                        <h3 class="product-name">Corsair Vengeance RGB 32GB</h3>
                        <p class="product-description">ذاكرة DDR5 بسرعة 6000MHz مع إضاءة RGB</p>
                        <div class="product-footer">
                            <span class="product-price">749 ريال</span>
                            <button class="product-btn" onclick="addToCart(this)">أضف للسلة</button>
                        </div>
                    </div>
                </div>

                <div class="product-card fade-in">
                    <div class="product-image">
                        <img src="samsung-ssd.png" alt="Samsung 990 PRO 2TB">
                    </div>
                    <div class="product-info">
                        <div class="product-category">تخزين</div>
                        <h3 class="product-name">Samsung 990 PRO 2TB</h3>
                        <p class="product-description">SSD NVMe فائق السرعة بمعدل قراءة 7,450 MB/s</p>
                        <div class="product-footer">
                            <span class="product-price">899 ريال</span>
                            <button class="product-btn" onclick="addToCart(this)">أضف للسلة</button>
                        </div>
                    </div>
                </div>

                <div class="product-card fade-in">
                    <div class="product-image">
                        <img src="evga-psu.png" alt="EVGA SuperNOVA 850W">
                    </div>
                    <div class="product-info">
                        <div class="product-category">مزودات الطاقة</div>
                        <h3 class="product-name">EVGA SuperNOVA 850W</h3>
                        <p class="product-description">مزود طاقة بكفاءة 80+ Gold وحماية كاملة</p>
                        <div class="product-footer">
                            <span class="product-price">599 ريال</span>
                            <button class="product-btn" onclick="addToCart(this)">أضف للسلة</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Use Cases Section -->
    <section id="use-cases" class="section">
        <div class="container">
            <div class="section-title">
                <h2>تجميعات مخصصة لكل احتياج</h2>
                <p>اختر التجميعة المناسبة حسب نوع استخدامك</p>
            </div>
            <div class="grid-3">
                <div class="use-case-card fade-in">
                    <span class="use-case-icon">👨‍🎓</span>
                    <h3 class="use-case-title">جهاز للطالب الجامعي</h3>
                    <p class="use-case-description">تجميعة متوازنة للدراسة والبحث واستخدام برامج الأوفيس</p>
                    <ul class="specs-list">
                        <li>معالج Intel Core i5 أو AMD Ryzen 5</li>
                        <li>ذاكرة 16GB RAM</li>
                        <li>وحدة تخزين SSD 512GB</li>
                        <li>كرت شاشة مدمج</li>
                        <li>السعر: 2,500 - 3,500 ريال</li>
                    </ul>
                </div>

                <div class="use-case-card fade-in">
                    <span class="use-case-icon">🎮</span>
                    <h3 class="use-case-title">جهاز للألعاب الإلكترونية</h3>
                    <p class="use-case-description">قوة أداء استثنائية للألعاب بدقة عالية ومعدل إطارات سلس</p>
                    <ul class="specs-list">
                        <li>معالج Intel Core i7 أو AMD Ryzen 7</li>
                        <li>كرت شاشة RTX 4070 أو أعلى</li>
                        <li>ذاكرة 32GB RAM</li>
                        <li>وحدة تخزين SSD 1TB NVMe</li>
                        <li>السعر: 7,000 - 10,000 ريال</li>
                    </ul>
                </div>

                <div class="use-case-card fade-in">
                    <span class="use-case-icon">🎨</span>
                    <h3 class="use-case-title">جهاز للتصميم والمونتاج</h3>
                    <p class="use-case-description">أداء احترافي لبرامج التصميم الجرافيكي ومونتاج الفيديو</p>
                    <ul class="specs-list">
                        <li>معالج متعدد الأنوية (12-16 نواة)</li>
                        <li>كرت شاشة بذاكرة 12GB VRAM أو أعلى</li>
                        <li>ذاكرة 32-64GB RAM</li>
                        <li>وحدة تخزين SSD 2TB</li>
                        <li>السعر: 9,000 - 15,000 ريال</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>عن المتجر</h3>
                    <p>متجر متخصص في بيع قطع الحاسب الآلي عالية الجودة مع تقديم محتوى تعليمي شامل لمساعدة العملاء</p>
                </div>
                <div class="footer-section">
                    <h3>روابط سريعة</h3>
                    <ul>
                        <li><a href="#home">الرئيسية</a></li>
                        <li><a href="#products">المنتجات</a></li>
                        <li><a href="#features">المميزات</a></li>
                        <li><a href="#use-cases">حالات الاستخدام</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>خدمة العملاء</h3>
                    <ul>
                        <li><a href="#">سياسة الاسترجاع</a></li>
                        <li><a href="#">الشحن والتوصيل</a></li>
                        <li><a href="#">الضمان</a></li>
                        <li><a href="#">الأسئلة الشائعة</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>تواصل معنا</h3>
                    <ul>
                        <li>📧 info@pcstore.sa</li>
                        <li>📱 +966 50 123 4567</li>
                        <li>📍 أبها، المملكة العربية السعودية</li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>© 2026 متجر قطع الحاسب الآلي. جميع الحقوق محفوظة.</p>
            </div>
        </div>
    </footer>

    <script>
        // Cart functionality
        let cartCount = 0;

        function addToCart(button) {
            const productName = button.closest('.product-card').querySelector('.product-name').textContent;
            
            // Haptic feedback on mobile
            if (window.navigator && window.navigator.vibrate) {
                window.navigator.vibrate(50);
            }
            
            button.textContent = '✓ تمت الإضافة';
            button.style.background = 'var(--kku-green)';
            button.disabled = true;
            
            cartCount++;
            document.getElementById('cart-count').textContent = cartCount;
            
            setTimeout(() => {
                button.textContent = 'أضف للسلة';
                button.style.background = 'var(--kku-gold)';
                button.disabled = false;
            }, 2000);
        }

        // Mobile menu toggle
        const menuToggle = document.getElementById('menuToggle');
        const navMenu = document.getElementById('navMenu');

        menuToggle.addEventListener('click', function() {
            navMenu.classList.toggle('show');
            this.textContent = navMenu.classList.contains('show') ? 'إغلاق ✕' : 'القائمة ☰';
        });

        // Close menu when clicking on a link
        document.querySelectorAll('#navMenu a').forEach(link => {
            link.addEventListener('click', function() {
                if (window.innerWidth <= 768) {
                    navMenu.classList.remove('show');
                    menuToggle.textContent = 'القائمة ☰';
                }
            });
        });

        // Smooth scroll function
        function scrollToSection(sectionId) {
            const section = document.getElementById(sectionId);
            if (section) {
                section.scrollIntoView({ behavior: 'smooth', block: 'start' });
            }
        }

        // Smooth scrolling for all anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });

        // Intersection Observer for fade-in animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        // Observe all fade-in elements
        document.querySelectorAll('.fade-in').forEach(el => {
            el.style.opacity = '0';
            observer.observe(el);
        });

        // Handle window resize
        window.addEventListener('resize', function() {
            if (window.innerWidth > 768) {
                navMenu.classList.remove('show');
                menuToggle.textContent = 'القائمة ☰';
            }
        });

        // Prevent text selection on double tap
        let lastTap = 0;
        document.addEventListener('touchend', function(e) {
            const currentTime = new Date().getTime();
            const tapLength = currentTime - lastTap;
            if (tapLength < 500 && tapLength > 0) {
                e.preventDefault();
            }
            lastTap = currentTime;
        });
    </script>
</body>
</html>
