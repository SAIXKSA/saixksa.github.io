
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>متجر قطع الحاسب الآلي - PC Hardware Store</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;800&family=Amiri:wght@400;700&display=swap" rel="stylesheet">
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
        }

        body {
            font-family: 'Cairo', sans-serif;
            background: linear-gradient(135deg, #f5f5f5 0%, #e8e8e8 100%);
            color: var(--dark);
            overflow-x: hidden;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, var(--kku-dark-green) 0%, var(--kku-green) 100%);
            padding: 0;
            box-shadow: 0 8px 24px rgba(26, 95, 63, 0.3);
            position: sticky;
            top: 0;
            z-index: 1000;
            animation: slideDown 0.6s ease-out;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-100%);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .header-top {
            background: var(--kku-dark-green);
            padding: 12px 0;
            border-bottom: 2px solid var(--kku-gold);
        }

        .header-top .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 30px;
        }

        .logo-section {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .logo {
            width: 70px;
            height: 70px;
            background: var(--white);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 32px;
            font-weight: 800;
            color: var(--kku-green);
            border: 3px solid var(--kku-gold);
            box-shadow: 0 4px 12px rgba(201, 150, 43, 0.4);
            transition: transform 0.3s ease;
        }

        .logo:hover {
            transform: rotate(360deg) scale(1.1);
        }

        .brand-text h1 {
            font-family: 'Amiri', serif;
            color: var(--kku-gold);
            font-size: 28px;
            font-weight: 700;
            margin-bottom: 4px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .brand-text p {
            color: var(--white);
            font-size: 14px;
            font-weight: 300;
            letter-spacing: 1px;
        }

        .header-actions {
            display: flex;
            gap: 25px;
        }

        .action-btn {
            background: transparent;
            border: 2px solid var(--kku-gold);
            color: var(--white);
            padding: 10px 24px;
            border-radius: 25px;
            cursor: pointer;
            font-family: 'Cairo', sans-serif;
            font-size: 15px;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .action-btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: var(--kku-gold);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
            z-index: -1;
        }

        .action-btn:hover::before {
            width: 300px;
            height: 300px;
        }

        .action-btn:hover {
            color: var(--kku-dark-green);
            border-color: var(--kku-gold);
        }

        /* Navigation */
        nav {
            background: var(--kku-green);
            padding: 18px 0;
        }

        nav .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 30px;
        }

        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            gap: 40px;
        }

        nav ul li a {
            color: var(--white);
            text-decoration: none;
            font-size: 17px;
            font-weight: 600;
            padding: 10px 20px;
            border-radius: 8px;
            transition: all 0.3s ease;
            position: relative;
        }

        nav ul li a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 50%;
            width: 0;
            height: 3px;
            background: var(--kku-gold);
            transform: translateX(-50%);
            transition: width 0.3s ease;
        }

        nav ul li a:hover {
            background: rgba(255, 255, 255, 0.1);
        }

        nav ul li a:hover::after {
            width: 80%;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--kku-green) 0%, var(--kku-light-green) 100%);
            padding: 80px 30px;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -10%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(201, 150, 43, 0.2) 0%, transparent 70%);
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
            max-width: 1400px;
            margin: 0 auto;
            text-align: center;
            position: relative;
            z-index: 1;
            animation: fadeInUp 0.8s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h2 {
            font-family: 'Amiri', serif;
            font-size: 56px;
            color: var(--white);
            margin-bottom: 20px;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.3);
            font-weight: 700;
        }

        .hero p {
            font-size: 22px;
            color: var(--white);
            margin-bottom: 35px;
            line-height: 1.8;
            max-width: 900px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero-btn {
            background: var(--kku-gold);
            color: var(--white);
            padding: 18px 50px;
            border: none;
            border-radius: 30px;
            font-size: 18px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.4s ease;
            box-shadow: 0 8px 20px rgba(201, 150, 43, 0.4);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .hero-btn:hover {
            background: var(--white);
            color: var(--kku-green);
            transform: translateY(-5px);
            box-shadow: 0 12px 28px rgba(201, 150, 43, 0.6);
        }

        /* Features Section */
        .features {
            padding: 80px 30px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-title h2 {
            font-family: 'Amiri', serif;
            font-size: 42px;
            color: var(--kku-green);
            margin-bottom: 15px;
            position: relative;
            display: inline-block;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, transparent, var(--kku-gold), transparent);
        }

        .section-title p {
            font-size: 18px;
            color: var(--gray);
            max-width: 700px;
            margin: 20px auto 0;
            line-height: 1.8;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 35px;
            margin-top: 50px;
        }

        .feature-card {
            background: var(--white);
            padding: 40px 30px;
            border-radius: 20px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.08);
            transition: all 0.4s ease;
            border-top: 5px solid var(--kku-gold);
            position: relative;
            overflow: hidden;
        }

        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--kku-green) 0%, var(--kku-light-green) 100%);
            opacity: 0;
            transition: all 0.6s ease;
            z-index: 0;
        }

        .feature-card:hover::before {
            left: 0;
            opacity: 0.95;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 45px rgba(26, 95, 63, 0.2);
        }

        .feature-card-content {
            position: relative;
            z-index: 1;
            transition: color 0.3s ease;
        }

        .feature-card:hover .feature-card-content h3,
        .feature-card:hover .feature-card-content p {
            color: var(--white);
        }

        .feature-icon {
            font-size: 52px;
            margin-bottom: 25px;
            transition: transform 0.4s ease;
        }

        .feature-card:hover .feature-icon {
            transform: scale(1.2) rotate(5deg);
        }

        .feature-card h3 {
            font-size: 24px;
            color: var(--kku-green);
            margin-bottom: 15px;
            font-weight: 700;
            transition: color 0.3s ease;
        }

        .feature-card p {
            font-size: 16px;
            color: var(--gray);
            line-height: 1.8;
            transition: color 0.3s ease;
        }

        /* Products Section */
        .products {
            padding: 80px 30px;
            background: var(--light-gray);
        }

        .products-container {
            max-width: 1400px;
            margin: 0 auto;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 35px;
            margin-top: 50px;
        }

        .product-card {
            background: var(--white);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.08);
            transition: all 0.4s ease;
            border: 3px solid transparent;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 45px rgba(26, 95, 63, 0.2);
            border-color: var(--kku-gold);
        }

        .product-image {
            height: 280px;
            background: linear-gradient(135deg, var(--kku-light-green) 0%, var(--kku-green) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            color: var(--white);
            position: relative;
            overflow: hidden;
        }

        .product-image::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.1) 0%, transparent 70%);
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            from {
                transform: rotate(0deg);
            }
            to {
                transform: rotate(360deg);
            }
        }

        .product-info {
            padding: 30px;
        }

        .product-category {
            color: var(--kku-gold);
            font-size: 14px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 10px;
        }

        .product-name {
            font-size: 22px;
            color: var(--kku-green);
            margin-bottom: 15px;
            font-weight: 700;
        }

        .product-description {
            font-size: 15px;
            color: var(--gray);
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .product-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 20px;
            padding-top: 20px;
            border-top: 2px solid var(--light-gray);
        }

        .product-price {
            font-size: 26px;
            color: var(--kku-green);
            font-weight: 800;
        }

        .product-btn {
            background: var(--kku-gold);
            color: var(--white);
            padding: 12px 28px;
            border: none;
            border-radius: 25px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 15px;
        }

        .product-btn:hover {
            background: var(--kku-green);
            transform: scale(1.05);
        }

        /* Use Cases Section */
        .use-cases {
            padding: 80px 30px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .use-cases-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            margin-top: 50px;
        }

        .use-case-card {
            background: linear-gradient(135deg, var(--white) 0%, var(--light-gray) 100%);
            padding: 45px;
            border-radius: 25px;
            box-shadow: 0 10px 35px rgba(0, 0, 0, 0.1);
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
            border-right: 6px solid var(--kku-gold);
        }

        .use-case-card::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(26, 95, 63, 0.05) 0%, transparent 70%);
            transition: transform 0.6s ease;
        }

        .use-case-card:hover::before {
            transform: scale(1.5);
        }

        .use-case-card:hover {
            transform: translateX(-10px);
            box-shadow: 0 15px 50px rgba(26, 95, 63, 0.15);
        }

        .use-case-icon {
            font-size: 64px;
            margin-bottom: 25px;
        }

        .use-case-title {
            font-size: 28px;
            color: var(--kku-green);
            margin-bottom: 20px;
            font-weight: 700;
        }

        .use-case-description {
            font-size: 16px;
            color: var(--gray);
            line-height: 1.8;
            margin-bottom: 25px;
        }

        .specs-list {
            list-style: none;
            margin-top: 20px;
        }

        .specs-list li {
            padding: 12px 0;
            border-bottom: 1px solid rgba(26, 95, 63, 0.1);
            color: var(--dark);
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .specs-list li::before {
            content: '✓';
            color: var(--kku-gold);
            font-weight: 800;
            font-size: 18px;
        }

        /* Footer */
        footer {
            background: linear-gradient(135deg, var(--kku-dark-green) 0%, var(--kku-green) 100%);
            color: var(--white);
            padding: 60px 30px 30px;
            margin-top: 80px;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-section h3 {
            font-family: 'Amiri', serif;
            font-size: 24px;
            margin-bottom: 20px;
            color: var(--kku-gold);
        }

        .footer-section p,
        .footer-section ul {
            font-size: 15px;
            line-height: 1.8;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 12px;
            transition: transform 0.3s ease;
        }

        .footer-section ul li:hover {
            transform: translateX(-5px);
        }

        .footer-section ul li a {
            color: var(--white);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-section ul li a:hover {
            color: var(--kku-gold);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 2px solid rgba(201, 150, 43, 0.3);
            font-size: 14px;
        }

        /* Animations */
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        .fade-in {
            animation: fadeIn 1s ease-out;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h2 {
                font-size: 36px;
            }

            .hero p {
                font-size: 18px;
            }

            nav ul {
                flex-direction: column;
                gap: 10px;
            }

            .header-actions {
                flex-direction: column;
                gap: 10px;
            }

            .products-grid,
            .features-grid,
            .use-cases-grid {
                grid-template-columns: 1fr;
            }

            .section-title h2 {
                font-size: 32px;
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
                    <button class="action-btn">سلة المشتريات (0)</button>
                </div>
            </div>
        </div>
        <nav>
            <div class="container">
                <ul>
                    <li><a href="#home">الرئيسية</a></li>
                    <li><a href="#products">المنتجات</a></li>
                    <li><a href="#features">المميزات</a></li>
                    <li><a href="#use-cases">حالات الاستخدام</a></li>
                    <li><a href="#about">من نحن</a></li>
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
            <button class="hero-btn" onclick="document.getElementById('products').scrollIntoView({behavior: 'smooth'})">استكشف المنتجات</button>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="features">
        <div class="section-title">
            <h2>لماذا نحن الخيار الأمثل؟</h2>
            <p>نقدم تجربة تسوق فريدة تجمع بين الجودة والمعرفة والشفافية</p>
        </div>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-card-content">
                    <div class="feature-icon">🎓</div>
                    <h3>محتوى تعليمي شامل</h3>
                    <p>شروحات تفصيلية لكل قطعة مع أمثلة واقعية وإرشادات واضحة تساعدك على فهم مكونات الحاسب واختيار الأنسب لك</p>
                </div>
            </div>
            <div class="feature-card">
                <div class="feature-card-content">
                    <div class="feature-icon">⚙️</div>
                    <h3>فحص التوافق التلقائي</h3>
                    <p>نظام ذكي يتحقق من توافق القطع مع بعضها البعض ويحذرك من أي مشكلة قبل إتمام الشراء</p>
                </div>
            </div>
            <div class="feature-card">
                <div class="feature-card-content">
                    <div class="feature-icon">💡</div>
                    <h3>اقتراحات مخصصة</h3>
                    <p>تجميعات جاهزة حسب نوع الاستخدام والميزانية، سواء للألعاب أو التصميم أو الاستخدام المكتبي</p>
                </div>
            </div>
            <div class="feature-card">
                <div class="feature-card-content">
                    <div class="feature-icon">🔍</div>
                    <h3>مقارنات تقنية</h3>
                    <p>قارن بين المنتجات المختلفة بناءً على المواصفات والأداء والأسعار لاتخاذ القرار الأفضل</p>
                </div>
            </div>
            <div class="feature-card">
                <div class="feature-card-content">
                    <div class="feature-icon">✅</div>
                    <h3>جودة مضمونة</h3>
                    <p>جميع المنتجات أصلية مع ضمان رسمي وخدمة ما بعد البيع الممتازة</p>
                </div>
            </div>
            <div class="feature-card">
                <div class="feature-card-content">
                    <div class="feature-icon">🚚</div>
                    <h3>شحن سريع وآمن</h3>
                    <p>توصيل سريع لجميع مناطق المملكة مع تغليف احترافي يضمن سلامة المنتجات</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="products">
        <div class="products-container">
            <div class="section-title">
                <h2>أحدث المنتجات</h2>
                <p>تشكيلة واسعة من قطع الحاسب عالية الجودة</p>
            </div>
            <div class="products-grid">
                <div class="product-card">
                    <div class="product-image">🖥️</div>
                    <div class="product-info">
                        <div class="product-category">معالجات</div>
                        <h3 class="product-name">Intel Core i7-14700K</h3>
                        <p class="product-description">معالج قوي بـ 20 نواة و28 خيط، مثالي للألعاب والتصميم والبرمجة المتقدمة</p>
                        <div class="product-footer">
                            <span class="product-price">1,899 ريال</span>
                            <button class="product-btn">أضف للسلة</button>
                        </div>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">🎮</div>
                    <div class="product-info">
                        <div class="product-category">كروت الشاشة</div>
                        <h3 class="product-name">NVIDIA RTX 4070 Ti</h3>
                        <p class="product-description">كرت شاشة احترافي بذاكرة 12GB GDDR6X لتجربة ألعاب استثنائية بدقة 4K</p>
                        <div class="product-footer">
                            <span class="product-price">3,499 ريال</span>
                            <button class="product-btn">أضف للسلة</button>
                        </div>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">💾</div>
                    <div class="product-info">
                        <div class="product-category">اللوحات الأم</div>
                        <h3 class="product-name">ASUS ROG STRIX Z790-E</h3>
                        <p class="product-description">لوحة أم متطورة بدعم DDR5 و PCIe 5.0 مع نظام تبريد متقدم</p>
                        <div class="product-footer">
                            <span class="product-price">1,299 ريال</span>
                            <button class="product-btn">أضف للسلة</button>
                        </div>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">🧠</div>
                    <div class="product-info">
                        <div class="product-category">ذاكرة عشوائية</div>
                        <h3 class="product-name">Corsair Vengeance RGB 32GB</h3>
                        <p class="product-description">ذاكرة DDR5 بسرعة 6000MHz مع إضاءة RGB قابلة للتخصيص</p>
                        <div class="product-footer">
                            <span class="product-price">749 ريال</span>
                            <button class="product-btn">أضف للسلة</button>
                        </div>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">💽</div>
                    <div class="product-info">
                        <div class="product-category">تخزين</div>
                        <h3 class="product-name">Samsung 990 PRO 2TB</h3>
                        <p class="product-description">SSD NVMe فائق السرعة بمعدل قراءة 7,450 MB/s</p>
                        <div class="product-footer">
                            <span class="product-price">899 ريال</span>
                            <button class="product-btn">أضف للسلة</button>
                        </div>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">⚡</div>
                    <div class="product-info">
                        <div class="product-category">مزودات الطاقة</div>
                        <h3 class="product-name">EVGA SuperNOVA 850W</h3>
                        <p class="product-description">مزود طاقة بكفاءة 80+ Gold وحماية كاملة للمكونات</p>
                        <div class="product-footer">
                            <span class="product-price">599 ريال</span>
                            <button class="product-btn">أضف للسلة</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Use Cases Section -->
    <section id="use-cases" class="use-cases">
        <div class="section-title">
            <h2>تجميعات مخصصة لكل احتياج</h2>
            <p>اختر التجميعة المناسبة حسب نوع استخدامك</p>
        </div>
        <div class="use-cases-grid">
            <div class="use-case-card">
                <div class="use-case-icon">👨‍🎓</div>
                <h3 class="use-case-title">جهاز للطالب الجامعي</h3>
                <p class="use-case-description">تجميعة متوازنة للدراسة والبحث واستخدام برامج الأوفيس بكفاءة عالية</p>
                <ul class="specs-list">
                    <li>معالج Intel Core i5 أو AMD Ryzen 5</li>
                    <li>ذاكرة 16GB RAM</li>
                    <li>وحدة تخزين SSD 512GB</li>
                    <li>كرت شاشة مدمج</li>
                    <li>السعر التقريبي: 2,500 - 3,500 ريال</li>
                </ul>
            </div>

            <div class="use-case-card">
                <div class="use-case-icon">🎮</div>
                <h3 class="use-case-title">جهاز للألعاب الإلكترونية</h3>
                <p class="use-case-description">قوة أداء استثنائية للألعاب بدقة عالية ومعدل إطارات سلس</p>
                <ul class="specs-list">
                    <li>معالج Intel Core i7 أو AMD Ryzen 7</li>
                    <li>كرت شاشة RTX 4070 أو أعلى</li>
                    <li>ذاكرة 32GB RAM</li>
                    <li>وحدة تخزين SSD 1TB NVMe</li>
                    <li>السعر التقريبي: 7,000 - 10,000 ريال</li>
                </ul>
            </div>

            <div class="use-case-card">
                <div class="use-case-icon">🎨</div>
                <h3 class="use-case-title">جهاز للتصميم والمونتاج</h3>
                <p class="use-case-description">أداء احترافي لبرامج التصميم الجرافيكي ومونتاج الفيديو</p>
                <ul class="specs-list">
                    <li>معالج متعدد الأنوية (12-16 نواة)</li>
                    <li>كرت شاشة بذاكرة 12GB VRAM أو أعلى</li>
                    <li>ذاكرة 32-64GB RAM</li>
                    <li>وحدة تخزين SSD 2TB</li>
                    <li>السعر التقريبي: 9,000 - 15,000 ريال</li>
                </ul>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="footer-content">
            <div class="footer-section">
                <h3>عن المتجر</h3>
                <p>متجر متخصص في بيع قطع الحاسب الآلي عالية الجودة مع تقديم محتوى تعليمي شامل لمساعدة العملاء على اتخاذ القرار الصحيح</p>
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
    </footer>

    <script>
        // Add smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add scroll animation for cards
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '0';
                    entry.target.style.transform = 'translateY(30px)';
                    setTimeout(() => {
                        entry.target.style.transition = 'all 0.6s ease-out';
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }, 100);
                }
            });
        }, observerOptions);

        document.querySelectorAll('.feature-card, .product-card, .use-case-card').forEach(card => {
            observer.observe(card);
        });

        // Add to cart functionality
        document.querySelectorAll('.product-btn').forEach(btn => {
            btn.addEventListener('click', function() {
                const productName = this.closest('.product-card').querySelector('.product-name').textContent;
                this.textContent = '✓ تمت الإضافة';
                this.style.background = 'var(--kku-green)';
                setTimeout(() => {
                    this.textContent = 'أضف للسلة';
                    this.style.background = 'var(--kku-gold)';
                }, 2000);
            });
        });
    </script>
</body>
</html>
