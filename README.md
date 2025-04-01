<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MobileAcc - Accesorios para Celulares</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Estilos generales */
        :root {
            --primary: #3a86ff;
            --secondary: #8338ec;
            --dark: #212529;
            --light: #f8f9fa;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
        }
        
        a {
            text-decoration: none;
            color: inherit;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        .btn {
            display: inline-block;
            padding: 10px 20px;
            border-radius: 5px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            border: none;
        }
        
        .btn-primary {
            background-color: var(--primary);
            color: white;
        }
        
        .btn-primary:hover {
            background-color: #2a75e6;
            transform: translateY(-2px);
        }
        
        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
        }
        
        .btn-outline:hover {
            background-color: var(--primary);
            color: white;
        }
        
        /* Header */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary);
        }
        
        .logo span {
            color: var(--secondary);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 20px;
        }
        
        nav ul li a {
            font-weight: 600;
            transition: color 0.3s;
        }
        
        nav ul li a:hover {
            color: var(--primary);
        }
        
        .cart-icon {
            position: relative;
        }
        
        .cart-count {
            position: absolute;
            top: -10px;
            right: -10px;
            background-color: var(--primary);
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 12px;
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--dark);
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 80px 0;
            text-align: center;
        }
        
        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 30px;
        }
        
        /* Categorías */
        .categories-section {
            padding: 60px 0;
            background-color: white;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 40px;
            font-size: 2rem;
            color: var(--dark);
        }
        
        .categories {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
        }
        
        .category-card {
            width: 250px;
            height: 150px;
            border-radius: 10px;
            overflow: hidden;
            position: relative;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }
        
        .category-card:hover {
            transform: translateY(-10px);
        }
        
        .category-image {
            width: 100%;
            height: 100%;
            background-size: cover;
            background-position: center;
            transition: transform 0.5s;
        }
        
        .category-card:hover .category-image {
            transform: scale(1.1);
        }
        
        .category-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to top, rgba(0,0,0,0.7), rgba(0,0,0,0.3));
            display: flex;
            align-items: flex-end;
            padding: 20px;
        }
        
        .category-name {
            color: white;
            font-size: 1.3rem;
            font-weight: 600;
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
        }
        
        @media (max-width: 768px) {
            .header-container {
                position: relative;
            }
            
            nav {
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background-color: white;
                box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
                padding: 20px;
                display: none;
            }
            
            nav.active {
                display: block;
            }
            
            nav ul {
                flex-direction: column;
            }
            
            nav ul li {
                margin: 10px 0;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .category-card {
                width: 200px;
                height: 120px;
            }
        }
        
        @media (max-width: 576px) {
            .hero {
                padding: 60px 0;
            }
            
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .section-title {
                font-size: 1.5rem;
            }
            
            .categories {
                gap: 15px;
            }
            
            .category-card {
                width: 160px;
                height: 100px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <a href="#" class="logo">Mobile<span>Acc</span></a>
            
            <nav id="mainNav">
                <ul>
                    <li><a href="#">Inicio</a></li>
                    <li><a href="#categories">Categorías</a></li>
                    <li><a href="#">Ofertas</a></li>
                    <li><a href="#">Contacto</a></li>
                </ul>
            </nav>
            
            <div class="cart-icon">
                <i class="fas fa-shopping-cart"></i>
                <span class="cart-count">0</span>
            </div>
            
            <button class="mobile-menu-btn" id="mobileMenuBtn">
                <i class="fas fa-bars"></i>
            </button>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Los Mejores Accesorios para tu Celular</h1>
            <p>Encuentra fundas, protectores, cargadores y más para todos los modelos de smartphones al mejor precio del mercado.</p>
            <a href="#categories" class="btn btn-outline">Explorar Categorías</a>
        </div>
    </section>

    <!-- Categorías -->
    <section id="categories" class="categories-section">
        <div class="container">
            <h2 class="section-title">Nuestras Categorías</h2>
            
            <div class="categories">
                <a href="#" class="category-card">
                    <div class="category-image" style="background-image: url('https://images.unsplash.com/photo-1603921326210-6edd2d60ca68?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80');"></div>
                    <div class="category-overlay">
                        <h3 class="category-name">Fundas</h3>
                    </div>
                </a>
                
                <a href="#" class="category-card">
                    <div class="category-image" style="background-image: url('https://images.unsplash.com/photo-1601784551446-20c9e07cdbdb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80');"></div>
                    <div class="category-overlay">
                        <h3 class="category-name">Protectores</h3>
                    </div>
                </a>
                
                <a href="#" class="category-card">
                    <div class="category-image" style="background-image: url('https://images.unsplash.com/photo-1605787020600-b9ebd5df1d07?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80');"></div>
                    <div class="category-overlay">
                        <h3 class="category-name">Cargadores</h3>
                    </div>
                </a>
                
                <a href="#" class="category-card">
                    <div class="category-image" style="background-image: url('https://images.unsplash.com/photo-1590658268037-6bf12165a8df?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80');"></div>
                    <div class="category-overlay">
                        <h3 class="category-name">Audífonos</h3>
                    </div>
                </a>
                
                <a href="#" class="category-card">
                    <div class="category-image" style="background-image: url('https://images.unsplash.com/photo-1605540436563-5bca919ae766?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80');"></div>
                    <div class="category-overlay">
                        <h3 class="category-name">Soportes</h3>
                    </div>
                </a>
            </div>
        </div>
    </section>

    <script>
        // Menú móvil
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const mainNav = document.getElementById('mainNav');

        mobileMenuBtn.addEventListener('click', () => {
            mainNav.classList.toggle('active');
        });
    </script>
</body>
</html>![1001245427](https://github.com/user-attachments/assets/a50e97be-b557-4d5b-baa2-9aba15b68a9b)
