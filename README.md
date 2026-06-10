<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AgroSustentável - Soluções para o Agronegócio</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-green: #2d6a4f;
            --secondary-green: #40916c;
            --light-green: #74c69d;
            --accent-gold: #d4a373;
            --dark: #1b4332;
            --light: #f8f9fa;
            --white: #ffffff;
            --shadow: 0 10px 40px rgba(0,0,0,0.1);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            color: #333;
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f1f1;
        }
        ::-webkit-scrollbar-thumb {
            background: var(--primary-green);
            border-radius: 4px;
        }
        
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255,255,255,0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 15px 0;
            box-shadow: 0 2px 20px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
        }
        
        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 30px;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
            font-weight: 800;
            font-size: 1.5rem;
            color: var(--primary-green);
            text-decoration: none;
        }
        
        .logo i {
            font-size: 2rem;
            color: var(--secondary-green);
        }
        
        .nav-links {
            display: flex;
            gap: 35px;
            list-style: none;
        }
        
        .nav-links a {
            text-decoration: none;
            color: #444;
            font-weight: 500;
            font-size: 0.95rem;
            transition: color 0.3s;
            position: relative;
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary-green);
            transition: width 0.3s;
        }
        
        .nav-links a:hover {
            color: var(--primary-green);
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        .nav-cta {
            background: var(--primary-green);
            color: white !important;
            padding: 10px 25px;
            border-radius: 30px;
            transition: all 0.3s !important;
        }
        
        .nav-cta:hover {
            background: var(--dark);
            transform: translateY(-2px);
        }
        
        .nav-cta::after {
            display: none !important;
        }
        
        .hero {
            min-height: 100vh;
            background: linear-gradient(135deg, rgba(45,106,79,0.9), rgba(27,67,50,0.85)),
                        url('https://images.unsplash.com/photo-1500382017468-9049fed747ef?w=1920') center/cover;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }
        
        .hero-content {
            max-width: 900px;
            padding: 0 30px;
            animation: fadeInUp 1s ease;
        }
        
        .hero-badge {
            display: inline-block;
            background: rgba(255,255,255,0.15);
            backdrop-filter: blur(10px);
            padding: 8px 25px;
            border-radius: 50px;
            font-size: 0.9rem;
            margin-bottom: 25px;
            border: 1px solid rgba(255,255,255,0.2);
        }
        
        .hero h1 {
            font-size: 3.5rem;
            font-weight: 800;
            line-height: 1.2;
            margin-bottom: 20px;
        }
        
        .hero h1 span {
            color: var(--light-green);
        }
        
        .hero p {
            font-size: 1.2rem;
            opacity: 0.9;
            margin-bottom: 40px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .hero-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        .btn {
            padding: 15px 40px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }
        
        .btn-primary {
            background: var(--light-green);
            color: var(--dark);
            border: none;
        }
        
        .btn-primary:hover {
            background: white;
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }
        
        .btn-outline {
            background: transparent;
            color: white;
            border: 2px solid rgba(255,255,255,0.5);
        }
        
        .btn-outline:hover {
            background: white;
            color: var(--dark);
            border-color: white;
        }
        
        .hero-stats {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: center;
            gap: 80px;
            padding: 40px;
            border-top: 1px solid rgba(255,255,255,0.1);
        }
        
        .stat-item {
            text-align: center;
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: 800;
            color: var(--light-green);
        }
        
        .stat-label {
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
        }
        
        .particle {
            position: absolute;
            width: 6px;
            height: 6px;
            background: rgba(255,255,255,0.3);
            border-radius: 50%;
            animation: float 15s infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100vh) rotate(720deg); opacity: 0; }
        }
        
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(40px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        section {
            padding: 100px 30px;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .section-header {
            text-align: center;
            margin-bottom: 70px;
        }
        
        .section-header h2 {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--dark);
            margin-bottom: 15px;
        }
        
        .section-header p {
            color: #666;
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .section-tag {
            display: inline-block;
            background: var(--light-green);
            color: var(--dark);
            padding: 5px 20px;
            border-radius: 50px;
            font-size: 0.85rem;
            font-weight: 600;
            margin-bottom: 15px;
        }
        
        .about {
            background: var(--light);
        }
        
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }
        
        .about-image {
            position: relative;
        }
        
        .about-image img {
            width: 100%;
            border-radius: 20px;
            box-shadow: var(--shadow);
        }
        
        .about-image::before {
            content: '';
            position: absolute;
            top: -20px;
            left: -20px;
            width: 100%;
            height: 100%;
            border: 3px solid var(--light-green);
            border-radius: 20px;
            z-index: -1;
        }
        
        .about-content h3 {
            font-size: 2rem;
            color: var(--dark);
            margin-bottom: 20px;
        }
        
        .about-content p {
            color: #555;
            margin-bottom: 20px;
            font-size: 1.05rem;
        }
        
        .about-features {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-top: 30px;
        }
        
        .about-feature {
            display: flex;
            align-items: flex-start;
            gap: 15px;
        }
        
        .about-feature i {
            font-size: 1.5rem;
            color: var(--primary-green);
            margin-top: 3px;
        }
        
        .about-feature h4 {
            font-size: 1rem;
            color: var(--dark);
            margin-bottom: 5px;
        }
        
        .about-feature p {
            font-size: 0.9rem;
            color: #777;
            margin: 0;
        }
        
        .cultures {
            background: white;
        }
        
        .cultures-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 30px;
        }
        
        .culture-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 5px 25px rgba(0,0,0,0.08);
            transition: all 0.4s ease;
            cursor: pointer;
            position: relative;
        }
        
        .culture-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 50px rgba(0,0,0,0.15);
        }
        
        .culture-card-image {
            height: 220px;
            overflow: hidden;
            position: relative;
        }
        
        .culture-card-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .culture-card:hover .culture-card-image img {
            transform: scale(1.1);
        }
        
        .culture-card-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(to top, rgba(0,0,0,0.7), transparent);
            display: flex;
            align-items: flex-end;
            padding: 20px;
        }
        
        .culture-icon {
            width: 50px;
            height: 50px;
            background: white;
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: var(--primary-green);
        }
        
        .culture-card-content {
            padding: 25px;
        }
        
        .culture-card-content h3 {
            font-size: 1.3rem;
            color: var(--dark);
            margin-bottom: 10px;
        }
        
        .culture-card-content p {
            color: #666;
            font-size: 0.95rem;
            margin-bottom: 20px;
        }
        
        .culture-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }
        
        .culture-tag {
            background: #e8f5e9;
            color: var(--primary-green);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
        }
        
        .solutions {
            background: linear-gradient(135deg, var(--dark), var(--primary-green));
            color: white;
            position: relative;
            overflow: hidden;
        }
        
        .solutions .section-header h2,
        .solutions .section-header p {
            color: white;
        }
        
        .solutions-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
        }
        
        .solution-card {
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.15);
            border-radius: 20px;
            padding: 40px 30px;
            transition: all 0.4s;
            position: relative;
            overflow: hidden;
        }
        
        .solution-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: var(--light-green);
            transform: scaleX(0);
            transition: transform 0.4s;
        }
        
        .solution-card:hover::before {
            transform: scaleX(1);
        }
        
        .solution-card:hover {
            background: rgba(255,255,255,0.15);
            transform: translateY(-5px);
        }
        
        .solution-icon {
            width: 70px;
            height: 70px;
            background: rgba(255,255,255,0.15);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            margin-bottom: 25px;
            color: var(--light-green);
        }
        
        .solution-card h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
        }
        
        .solution-card p {
            opacity: 0.85;
            font-size: 0.95rem;
            line-height: 1.7;
        }
        
        .solution-list {
            list-style: none;
            margin-top: 20px;
        }
        
        .solution-list li {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 10px;
            font-size: 0.9rem;
            opacity: 0.9;
        }
        
        .solution-list li i {
            color: var(--light-green);
        }
        
        .impact {
            background: var(--light);
        }
        
        .impact-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 30px;
        }
        
        .impact-card {
            background: white;
            border-radius: 20px;
            padding: 40px 30px;
            text-align: center;
            box-shadow: 0 5px 25px rgba(0,0,0,0.05);
            transition: all 0.4s;
            position: relative;
            overflow: hidden;
        }
        
        .impact-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow);
        }
        
        .impact-card::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: var(--primary-green);
        }
        
        .impact-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, var(--light-green), var(--secondary-green));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: white;
            margin: 0 auto 25px;
        }
        
        .impact-card h3 {
            font-size: 2.5rem;
            color: var(--primary-green);
            margin-bottom: 10px;
        }
        
        .impact-card p {
            color: #666;
            font-weight: 500;
        }
        
        .testimonials {
            background: white;
        }
        
        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
        }
        
        .testimonial-card {
            background: var(--light);
            border-radius: 20px;
            padding: 40px;
            position: relative;
        }
        
        .testimonial-card::before {
            content: '"';
            font-size: 5rem;
            color: var(--light-green);
            position: absolute;
            top: 10px;
            left: 20px;
            font-family: Georgia, serif;
            opacity: 0.5;
        }
        
        .testimonial-text {
            font-style: italic;
            color: #555;
            margin-bottom: 25px;
            line-height: 1.8;
            position: relative;
            z-index: 1;
        }
        
        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .testimonial-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--primary-green);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: 700;
        }
        
        .testimonial-info h4 {
            color: var(--dark);
            font-size: 1rem;
        }
        
        .testimonial-info p {
            color: #888;
            font-size: 0.85rem;
        }
        
        .cta {
            background: linear-gradient(135deg, var(--primary-green), var(--dark));
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }
        
        .cta h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }
        
        .cta p {
            font-size: 1.1rem;
            opacity: 0.9;
            max-width: 600px;
            margin: 0 auto 40px;
        }
        
        .cta-form {
            display: flex;
            gap: 15px;
            justify-content: center;
            max-width: 500px;
            margin: 0 auto;
        }
        
        .cta-form input {
            flex: 1;
            padding: 15px 25px;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            outline: none;
        }
        
        .cta-form button {
            padding: 15px 35px;
            background: var(--light-green);
            color: var(--dark);
            border: none;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .cta-form button:hover {
            background: white;
            transform: translateY(-2px);
        }
        
        footer {
            background: var(--dark);
            color: white;
            padding: 80px 30px 30px;
        }
        
        .footer-grid {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 50px;
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .footer-brand p {
            opacity: 0.7;
            margin: 20px 0;
            line-height: 1.8;
        }
        
        .footer-social {
            display: flex;
            gap: 15px;
        }
        
        .footer-social a {
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            transition: all 0.3s;
            text-decoration: none;
        }
        
        .footer-social a:hover {
            background: var(--light-green);
            color: var(--dark);
            transform: translateY(-3px);
        }
        
        .footer-links h4 {
            font-size: 1.1rem;
            margin-bottom: 25px;
            color: var(--light-green);
        }
        
        .footer-links ul {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 12px;
        }
        
        .footer-links a {
            color: rgba(255,255,255,0.7);
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: var(--light-green);
        }
        
        .footer-bottom {
            max-width: 1400px;
            margin: 60px auto 0;
            padding-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
            text-align: center;
            opacity: 0.6;
            font-size: 0.9rem;
        }
        
        .scroll-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background: var(--primary-green);
            color: white;
            border: none;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            box-shadow: 0 5px 20px rgba(0,0,0,0.2);
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
            z-index: 999;
        }
        
        .scroll-top.visible {
            opacity: 1;
            visibility: visible;
        }
        
        .scroll-top:hover {
            background: var(--dark);
            transform: translateY(-3px);
        }
        
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }
        
        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        @media (max-width: 1200px) {
            .cultures-grid { grid-template-columns: repeat(2, 1fr); }
            .solutions-grid { grid-template-columns: repeat(2, 1fr); }
            .impact-grid { grid-template-columns: repeat(2, 1fr); }
        }
        
        @media (max-width: 900px) {
            .nav-links { display: none; }
            .hero h1 { font-size: 2.5rem; }
            .hero-stats { gap: 30px; padding: 30px 20px; }
            .about-grid { grid-template-columns: 1fr; }
            .cultures-grid { grid-template-columns: 1fr; }
            .solutions-grid { grid-template-columns: 1fr; }
            .testimonials-grid { grid-template-columns: 1fr; }
            .impact-grid { grid-template-columns: 1fr 1fr; }
            .footer-grid { grid-template-columns: 1fr 1fr; }
            .cta-form { flex-direction: column; }
        }
        
        @media (max-width: 600px) {
            .hero h1 { font-size: 2rem; }
            .hero-stats { flex-direction: column; gap: 20px; }
            .impact-grid { grid-template-columns: 1fr; }
            .footer-grid { grid-template-columns: 1fr; }
            section { padding: 60px 20px; }
        }
    </style>
</head>
<body>

    <nav class="navbar">
        <div class="nav-container">
            <a href="#" class="logo">
                <i class="fas fa-leaf"></i>
                AgroSustentável
            </a>
            <ul class="nav-links">
                <li><a href="#home">Início</a></li>
                <li><a href="#sobre">Sobre</a></li>
                <li><a href="#culturas">Culturas</a></li>
                <li><a href="#solucoes">Soluções</a></li>
                <li><a href="#impacto">Impacto</a></li>
                <li><a href="#contato" class="nav-cta">Fale Conosco</a></li>
            </ul>
        </div>
    </nav>

    <section class="hero" id="home">
        <div class="particles" id="particles"></div>
        <div class="hero-content">
            <div class="hero-badge">
                <i class="fas fa-seedling"></i> Inovação em Agronegócio Sustentável
            </div>
            <h1>Transformando o <span>Agronegócio</span> com Soluções Sustentáveis</h1>
            <p>Tecnologia de ponta aliada à preservação ambiental para maximizar a produtividade de cana, milho, soja e piscicultura de forma responsável.</p>
            <div class="hero-buttons">
                <a href="#culturas" class="btn btn-primary">
                    <i class="fas fa-arrow-right"></i> Conheça Nossas Soluções
                </a>
                <a href="#sobre" class="btn btn-outline">
                    <i class="fas fa-play-circle"></i> Saiba Mais
                </a>
            </div>
        </div>
        <div class="hero-stats">
            <div class="stat-item">
                <div class="stat-number" data-count="500">0</div>
                <div class="stat-label">+ Produtores Atendidos</div>
            </div>
            <div class="stat-item">
                <div class="stat-number" data-count="120">0</div>
                <div class="stat-label">Mil Hectares Monitorados</div>
            </div>
            <div class="stat-item">
                <div class="stat-number" data-count="35">0</div>
                <div class="stat-label">% Aumento na Produtividade</div>
            </div>
            <div class="stat-item">
                <div class="stat-number" data-count="40">0</div>
                <div class="stat-label">% Redução de Impacto Ambiental</div>
            </div>
        </div>
    </section>

    <section class="about" id="sobre">
        <div class="container">
            <div class="about-grid">
                <div class="about-image fade-in">
                    <img src="https://images.unsplash.com/photo-1625246333195-78d9c38ad449?w=800" alt="Agricultura Sustentável">
                </div>
                <div class="about-content fade-in">
                    <span class="section-tag">Quem Somos</span>
                    <h3>Liderando a Revolução Verde no Agronegócio Brasileiro</h3>
                    <p>A AgroSustentável nasceu da convicção de que é possível conciliar alta produtividade agrícola com responsabilidade ambiental. Atuamos como parceiros estratégicos de produtores rurais, oferecendo soluções tecnológicas integradas que otimizam recursos naturais e maximizam resultados.</p>
                    <p>Nossa equipe multidisciplinar combina expertise em agronomia, engenharia ambiental, ciência de dados e sustentabilidade para entregar projetos que realmente fazem a diferença no campo e no planeta.</p>
                    <div class="about-features">
                        <div class="about-feature">
                            <i class="fas fa-satellite-dish"></i>
                            <div>
                                <h4>Monitoramento por Satélite</h4>
                                <p>Análise precisa em tempo real</p>
                            </div>
                        </div>
                        <div class="about-feature">
                            <i class="fas fa-water"></i>
                            <div>
                                <h4>Gestão Hídrica Inteligente</h4>
                                <p>Uso eficiente da água</p>
                            </div>
                        </div>
                        <div class="about-feature">
                            <i class="fas fa-bolt"></i>
                            <div>
                                <h4>Energia Renovável</h4>
                                <p>Soluções de biogás e solar</p>
                            </div>
                        </div>
                        <div class="about-feature">
                            <i class="fas fa-chart-line"></i>
                            <div>
                                <h4>Análise de Dados</h4>
                                <p>Inteligência para decisões</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="cultures" id="culturas">
        <div class="container">
            <div class="section-header fade-in">
                <span class="section-tag">Nossas Culturas</span>
                <h2>Soluções por Segmento</h2>
                <p>Especialização profunda em cada cultura para entregar resultados excepcionais com sustentabilidade comprovada.</p>
            </div>
            <div class="cultures-grid">
                <div class="culture-card fade-in">
                    <div class="culture-card-image">
                        <img src="https://images.unsplash.com/photo-1591086700348-d4f1c02b6e2e?w=600" alt="Cana-de-Açúcar">
                        <div class="culture-card-overlay">
                            <div class="culture-icon"><i class="fas fa-cubes"></i></div>
                        </div>
                    </div>
                    <div class="culture-card-content">
                        <h3>Cana-de-Açúcar</h3>
                        <p>Otimização do ciclo produtivo com foco em bioenergia, controle de pragas integrado e gestão sustentável de resíduos.</p>
                        <div class="culture-tags">
                            <span class="culture-tag">Bioenergia</span>
                            <span class="culture-tag">Vinhoto</span>
                            <span class="culture-tag">Colheita Mecanizada</span>
                        </div>
                    </div>
                </div>
                
                <div class="culture-card fade-in">
                    <div class="culture-card-image">
                        <img src="https://images.unsplash.com/photo-1551754655-cd27e38d2076?w=600" alt="Milho">
                        <div class="culture-card-overlay">
                            <div class="culture-icon"><i class="fas fa-corn"></i></div>
                        </div>
                    </div>
                    <div class="culture-card-content">
                        <h3>Milho</h3>
                        <p>Maximização da produtividade por hectare com rotação de culturas, nutrição de precisão e manejo integrado de doenças.</p>
                        <div class="culture-tags">
                            <span class="culture-tag">Safrinha</span>
                            <span class="culture-tag">Silagem</span>
                            <span class="culture-tag">Precisão</span>
                        </div>
                    </div>
                </div>
                
                <div class="culture-card fade-in">
                    <div class="culture-card-image">
                        <img src="https://images.unsplash.com/photo-1615485290382-441e4d049cb5?w=600" alt="Soja">
                        <div class="culture-card-overlay">
                            <div class="culture-icon"><i class="fas fa-seedling"></i></div>
                        </div>
                    </div>
                    <div class="culture-card-content">
                        <h3>Soja</h3>
                        <p>Produção sustentável com certificação RTRS, manejo de solos de Cerrado e sistemas de plantio direto na palha.</p>
                        <div class="culture-tags">
                            <span class="culture-tag">RTRS</span>
                            <span class="culture-tag">Plantio Direto</span>
                            <span class="culture-tag">Fixação N</span>
                        </div>
                    </div>
                </div>
                
                <div class="culture-card fade-in">
                    <div class="culture-card-image">
                        <img src="https://images.unsplash.com/photo-1544552866-d3ed42536cfd?w=600" alt="Piscicultura">
                        <div class="culture-card-overlay">
                            <div class="culture-icon"><i class="fas fa-fish"></i></div>
                        </div>
                    </div>
                    <div class="culture-card-content">
                        <h3>Piscicultura</h3>
                        <p>Sistemas de criação sustentável com recirculação de água, alimentação otimizada e gestão integrada de tanques.</p>
                        <div class="culture-tags">
                            <span class="culture-tag">RAS</span>
                            <span class="culture-tag">Tilápia</span>
                            <span class="culture-tag">Bioflocos</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="solutions" id="solucoes">
        <div class="container">
            <div class="section-header fade-in">
                <span class="section-tag">Nossas Soluções</span>
                <h2>Tecnologia ao Serviço da Sustentabilidade</h2>
                <p>Um ecossistema integrado de ferramentas e serviços para transformar sua operação agrícola.</p>
            </div>
            <div class="solutions-grid">
                <div class="solution-card fade-in">
                    <div class="solution-icon"><i class="fas fa-satellite"></i></div>
                    <h3>Monitoramento por Satélite</h3>
                    <p>Imagens de alta resolução com análise de NDVI, umidade do solo e detecção precoce de pragas e doenças.</p>
                    <ul class="solution-list">
                        <li><i class="fas fa-check-circle"></i> Alertas em tempo real</li>
                        <li><i class="fas fa-check-circle"></i> Mapeamento de produtividade</li>
                        <li><i class="fas fa-check-circle"></i> Zoneamento agrícola</li>
                    </ul>
                </div>
                
                <div class="solution-card fade-in">
                    <div class="solution-icon"><i class="fas fa-tint"></i></div>
                    <h3>Gestão Hídrica Inteligente</h3>
                    <p>Sistemas de irrigação de precisão com sensores de umidade e previsão meteorológica integrada.</p>
                    <ul class="solution-list">
                        <li><i class="fas fa-check-circle"></i> Economia de até 40% de água</li>
                        <li><i class="fas fa-check-circle"></i> Irrigação automatizada</li>
                        <li><i class="fas fa-check-circle"></i> Monitoramento de aquíferos</li>
                    </ul>
                </div>
                
                <div class="solution-card fade-in">
                    <div class="solution-icon"><i class="fas fa-bacteria"></i></div>
                    <h3>Manejo Integrado de Pragas</h3>
                    <p>Controle biológico e químico racional com drones e armadilhas inteligentes para proteção das culturas.</p>
                    <ul class="solution-list">
                        <li><i class="fas fa-check-circle"></i> Redução de agrotóxicos</li>
                        <li><i class="fas fa-check-circle"></i> Inimigos naturais</li>
                        <li><i class="fas fa-check-circle"></i> Pulverização de precisão</li>
                    </ul>
                </div>
                
                <div class="solution-card fade-in">
                    <div class="solution-icon"><i class="fas fa-solar-panel"></i></div>
                    <h3>Energia Renovável no Campo</h3>
                    <p>Implantação de sistemas fotovoltaicos e aproveitamento de biomassa para autossuficiência energética.</p>
                    <ul class="solution-list">
                        <li><i class="fas fa-check-circle"></i> Biogás de vinhoto</li>
                        <li><i class="fas fa-check-circle"></i> Energia solar fotovoltaica</li>
                        <li><i class="fas fa-check-circle"></i> Biodiesel de óleo de soja</li>
                    </ul>
                </div>
                
                <div class="solution-card fade-in">
                    <div class="solution-icon"><i class="fas fa-database"></i></div>
                    <h3>Big Data & Analytics</h3>
                    <p>Plataforma de inteligência artificial para previsão de safras, preços e recomendações personalizadas.</p>
                    <ul class="solution-list">
                        <li><i class="fas fa-check-circle"></i> Previsão de produtividade</li>
                        <li><i class="fas fa-check-circle"></i> Análise de mercado</li>
                        <li><i class="fas fa-check-circle"></i> Dashboards interativos</li>
                    </ul>
                </div>
                
                <div class="solution-card fade-in">
                    <div class="solution-icon"><i class="fas fa-certificate"></i></div>
                    <h3>Certificações Sustentáveis</h3>
                    <p>Consultoria completa para obtenção de selos de sustentabilidade e acesso a mercados premium.</p>
                    <ul class="solution-list">
                        <li><i class="fas fa-check-circle"></i> Certificação RTRS</li>
                        <li><i class="fas fa-check-circle"></i> Bonsucro</li>
                        <li><i class="fas fa-check-circle"></i> ASC para piscicultura</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <section class="impact" id="impacto">
        <div class="container">
            <div class="section-header fade-in">
                <span class="section-tag">Nosso Impacto</span>
                <h2>Resultados que Transformam</h2>
                <p>Números que comprovam nosso compromisso com a produtividade e o meio ambiente.</p>
            </div>
            <div class="impact-grid">
                <div class="impact-card fade-in">
                    <div class="impact-icon"><i class="fas fa-leaf"></i></div>
                    <h3 class="counter" data-target="85000">0</h3>
                    <p>Toneladas de CO₂ Evitadas</p>
                </div>
                <div class="impact-card fade-in">
                    <div class="impact-icon"><i class="fas fa-water"></i></div>
                    <h3 class="counter" data-target="1200">0</h3>
                    <p>Milhões de Litros de Água Economizados</p>
                </div>
                <div class="impact-card fade-in">
                    <div class="impact-icon"><i class="fas fa-tree"></i></div>
                    <h3 class="counter" data-target="45000">0</h3>
                    <p>Hectares sob Manejo Sustentável</p>
                </div>
                <div class="impact-card fade-in">
                    <div class="impact-icon"><i class="fas fa-users"></i></div>
                    <h3 class="counter" data-target="320">0</h3>
                    <p>Famílias Produtoras Impactadas</p>
                </div>
            </div>
        </div>
    </section>

    <section class="testimonials">
        <div class="container">
            <div class="section-header fade-in">
                <span class="section-tag">Depoimentos</span>
                <h2>O que Dizem Nossos Parceiros</h2>
                <p>Histórias reais de produtores que transformaram suas operações com nossas soluções.</p>
            </div>
            <div class="testimonials-grid">
                <div class="testimonial-card fade-in">
                    <p class="testimonial-text">"Implementamos o sistema de monitoramento por satélite na nossa usina de cana e conseguimos reduzir em 30% o uso de defensivos agrícolas. A produtividade aumentou e o impacto ambiental diminuiu significativamente."</p>
                    <div class="testimonial-author">
                        <div class="testimonial-avatar">RC</div>
                        <div class="testimonial-info">
                            <h4>Roberto Campos</h4>
                            <p>Usina Verde Vale - SP</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card fade-in">
                    <p class="testimonial-text">"A gestão hídrica inteligente revolucionou nossa produção de milho safrinha. Economizamos água, reduzimos custos e aumentamos o rendimento por hectare em 22%. Investimento que se pagou no primeiro ano."</p>
                    <div class="testimonial-author">
                        <div class="testimonial-avatar">MF</div>
                        <div class="testimonial-info">
                            <h4>Mariana Ferreira</h4>
                            <p>Fazenda Boa Vista - MT</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card fade-in">
                    <p class="testimonial-text">"Nosso projeto de piscicultura em sistema RAS com a AgroSustentável nos permitiu triplicar a produção de tilápia usando a mesma área de tanques. A qualidade da água e dos peixes melhorou drasticamente."</p>
                    <div class="testimonial-author">
                        <div class="testimonial-avatar">AS</div>
                        <div class="testimonial-info">
                            <h4>Antônio Silva</h4>
                            <p>Piscicultura Lagoa Azul - GO</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="cta" id="contato">
        <div class="container">
            <h2 class="fade-in">Pronto para Revolucionar sua Produção?</h2>
            <p class="fade-in">Entre em contato e descubra como nossas soluções sustentáveis podem transformar seu agronegócio. Nossa equipe de especialistas está pronta para atender você.</p>
            <div class="cta-form fade-in">
                <input type="email" placeholder="Digite seu melhor e-mail">
                <button><i class="fas fa-paper-plane"></i> Quero Saber Mais</button>
            </div>
        </div>
    </section>

    <footer>
        <div class="footer-grid">
            <div class="footer-brand">
                <a href="#" class="logo" style="color: white;">
                    <i class="fas fa-leaf"></i>
                    AgroSustentável
                </a>
                <p>Transformando o agronegócio brasileiro através de soluções inovadoras e sustentáveis. Nosso compromisso é com a produtividade, a rentabilidade e a preservação do meio ambiente.</p>
                <div class="footer-social">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-linkedin-in"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                    <a href="#"><i class="fab fa-whatsapp"></i></a>
                </div>
            </div>
            <div class="footer-links">
                <h4>Culturas</h4>
                <ul>
                    <li><a href="#">Cana-de-Açúcar</a></li>
                    <li><a href="#">Milho</a></li>
                    <li><a href="#">Soja</a></li>
                    <li><a href="#">Piscicultura</a></li>
                </ul>
            </div>
            <div class="footer-links">
                <h4>Soluções</h4>
                <ul>
                    <li><a href="#">Monitoramento Satelital</a></li>
                    <li><a href="#">Gestão Hídrica</a></li>
                    <li><a href="#">Energia Renovável</a></li>
                    <li><a href="#">Certificações</a></li>
                </ul>
            </div>
            <div class="footer-links">
                <h4>Contato</h4>
                <ul>
                    <li><a href="#"><i class="fas fa-map-marker-alt"></i> Av. Brasil, 1500 - São Paulo/SP</a></li>
                    <li><a href="#"><i class="fas fa-phone"></i> (11) 3456-7890</a></li>
                    <li><a href="#"><i class="fas fa-envelope"></i> contato@agrosustentavel.com.br</a></li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>© 2026 AgroSustentável. Todos os direitos reservados. | Desenvolvido com <i class="fas fa-heart" style="color: var(--light-green);"></i> para um futuro mais verde.</p>
        </div>
    </footer>

    <button class="scroll-top" id="scrollTop">
        <i class="fas fa-arrow-up"></i>
    </button>

    <script>
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 30; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDelay = Math.random() * 15 + 's';
            particle.style.animationDuration = (10 + Math.random() * 10) + 's';
            particle.style.width = (3 + Math.random() * 5) + 'px';
            particle.style.height = particle.style.width;
            particlesContainer.appendChild(particle);
        }

        const fadeElements = document.querySelectorAll('.fade-in');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.1 });
        
        fadeElements.forEach(el => observer.observe(el));

        const counters = document.querySelectorAll('.counter');
        const counterObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const counter = entry.target;
                    const target = parseInt(counter.getAttribute('data-target'));
                    const duration = 2000;
                    const step = target / (duration / 16);
                    let current = 0;
                    
                    const updateCounter = () => {
                        current += step;
                        if (current < target) {
                            counter.textContent = Math.floor(current).toLocaleString('pt-BR');
                            requestAnimationFrame(updateCounter);
                        } else {
                            counter.textContent = target.toLocaleString('pt-BR');
                        }
                    };
                    updateCounter();
                    counterObserver.unobserve(counter);
                }
            });
        }, { threshold: 0.5 });
        
        counters.forEach(counter => counterObserver.observe(counter));

        const heroStats = document.querySelectorAll('.stat-number');
        const heroObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const stat = entry.target;
                    const target = parseInt(stat.getAttribute('data-count'));
                    const duration = 2000;
                    const step = target / (duration / 16);
                    let current = 0;
                    
                    const updateStat = () => {
                        current += step;
                        if (current < target) {
                            stat.textContent = Math.floor(current) + '+';
                            requestAnimationFrame(updateStat);
                        } else {
                            stat.textContent = target + '+';
                        }
                    };
                    updateStat();
                    heroObserver.unobserve(stat);
                }
            });
        }, { threshold: 0.5 });
        
        heroStats.forEach(stat => heroObserver.observe(stat));

        const scrollTopBtn = document.getElementById('scrollTop');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 500) {
                scrollTopBtn.classList.add('visible');
            } else {
                scrollTopBtn.classList.remove('visible');
            }
            
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 50) {
                navbar.style.boxShadow = '0 2px 30px rgba(0,0,0,0.1)';
            } else {
                navbar.style.boxShadow = '0 2px 20px rgba(0,0,0,0.05)';
            }
        });
        
        scrollTopBtn.addEventListener('click', () => {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        });

        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });
    </script>
</body>
</html>
