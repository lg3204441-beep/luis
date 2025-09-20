<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YouCine Clone - Filmes e Séries</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        /*
        * CSS - ESTILOS DO SITE
        * Inclui as variáveis de cor, layouts e animações para temas dark e light.
        */

        /* Variáveis de Cor para Temas */
        :root {
            --dark-bg: #141414;
            --dark-card: #222;
            --dark-text: #fff;
            --dark-text-secondary: #aaa;
            --accent-color: #E50914;

            --light-bg: #f0f2f5;
            --light-card: #fff;
            --light-text: #333;
            --light-text-secondary: #666;
            --light-accent-color: #ff4d4d;

            --transition-speed: 0.3s;
        }

        /* Estilos de Base */
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            line-height: 1.6;
            scroll-behavior: smooth;
            transition: background-color var(--transition-speed), color var(--transition-speed);
        }

        /* Tema Escuro (Padrão) */
        body.dark-theme {
            background-color: var(--dark-bg);
            color: var(--dark-text);
        }

        body.dark-theme a {
            color: var(--dark-text);
        }

        /* Tema Claro */
        body.light-theme {
            background-color: var(--light-bg);
            color: var(--light-text);
        }

        body.light-theme a {
            color: var(--light-text);
        }

        /* Header */
        .header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 40px;
            background: rgba(20, 20, 20, 0.9);
            z-index: 1000;
            transition: background var(--transition-speed);
        }

        .light-theme .header {
            background: rgba(240, 242, 245, 0.9);
        }

        .logo {
            font-weight: 700;
            font-size: 1.5rem;
            color: var(--accent-color);
        }

        .nav-list {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        .nav-list a {
            text-decoration: none;
            font-weight: 600;
            transition: color 0.3s;
        }

        .nav-list a:hover {
            color: var(--accent-color);
        }

        .hamburger {
            display: none;
            background: none;
            border: none;
            cursor: pointer;
        }

        .bar {
            display: block;
            width: 25px;
            height: 3px;
            margin: 5px auto;
            background-color: var(--dark-text);
            transition: all 0.3s ease-in-out;
        }

        .light-theme .bar {
            background-color: var(--light-text);
        }

        .header-right {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        /* Botão de Alternar Tema */
        .theme-toggle {
            background: none;
            border: 1px solid var(--dark-text-secondary);
            color: var(--dark-text-secondary);
            border-radius: 50%;
            width: 40px;
            height: 40px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .light-theme .theme-toggle {
            border: 1px solid var(--light-text-secondary);
            color: var(--light-text-secondary);
        }

        .theme-toggle:hover {
            background-color: var(--accent-color);
            color: #fff;
            border-color: var(--accent-color);
        }

        .theme-toggle .icon-sun, .theme-toggle .icon-moon {
            font-size: 1.2rem;
            display: none;
        }
        .dark-theme .theme-toggle .icon-moon { display: block; }
        .light-theme .theme-toggle .icon-sun { display: block; }

        /* Seções */
        .section {
            padding: 100px 40px 40px;
            min-height: 80vh;
        }

        /* Hero Banner */
        .hero-banner {
            background: url('https://images.unsplash.com/photo-1627764724606-258607149a46?ixlib=rb-4.0.3&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=1920&h=1080&fit=crop') no-repeat center center/cover;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: flex-start;
            color: #fff;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            max-width: 600px;
            padding: 20px;
            background: rgba(0, 0, 0, 0.4);
            border-radius: 10px;
        }

        .hero-content h1 {
            font-size: 3rem;
            margin-bottom: 10px;
        }

        .hero-content p {
            font-size: 1.2rem;
            margin-bottom: 20px;
        }

        /* Botão */
        .btn {
            display: inline-block;
            padding: 12px 25px;
            background-color: var(--accent-color);
            color: #fff;
            text-decoration: none;
            border-radius: 5px;
            transition: background-color 0.3s ease;
        }

        .btn:hover {
            background-color: #ff333d;
        }

        /* Grid de Cards */
        .card-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            padding-top: 20px;
        }

        .movie-card {
            position: relative;
            overflow: hidden;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
            background-color: var(--dark-card);
        }

        .light-theme .movie-card {
            background-color: var(--light-card);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .movie-card:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.4);
        }

        .movie-card img {
            width: 100%;
            height: auto;
            display: block;
        }

        .card-info {
            padding: 15px;
            text-align: center;
            color: var(--dark-text);
        }

        .light-theme .card-info {
            color: var(--light-text);
        }

        /* Formulário de Contato */
        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 20px;
            max-width: 600px;
            margin: 0 auto;
        }

        .contact-form input,
        .contact-form textarea {
            padding: 12px;
            border: 1px solid var(--dark-text-secondary);
            background-color: transparent;
            border-radius: 5px;
            color: var(--dark-text);
            transition: border-color 0.3s ease;
        }

        .light-theme .contact-form input,
        .light-theme .contact-form textarea {
            border: 1px solid var(--light-text-secondary);
            color: var(--light-text);
        }

        .contact-form input:focus,
        .contact-form textarea:focus {
            border-color: var(--accent-color);
            outline: none;
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 20px;
            background-color: var(--dark-card);
            color: var(--dark-text-secondary);
        }

        .light-theme .footer {
            background-color: var(--light-card);
            color: var(--light-text-secondary);
        }

        /* Responsividade */
        @media (max-width: 768px) {
            .header {
                padding: 20px;
            }

            .nav {
                position: fixed;
                top: 0;
                right: -100%;
                height: 100%;
                width: 70%;
                background: var(--dark-card);
                display: flex;
                justify-content: center;
                align-items: center;
                flex-direction: column;
                transition: right 0.3s ease-in-out;
            }

            .light-theme .nav {
                background: var(--light-card);
            }

            .nav.open {
                right: 0;
            }

            .nav-list {
                flex-direction: column;
                gap: 20px;
                text-align: center;
            }
            
            .hamburger {
                display: block;
            }
        }
    </style>
</head>
<body class="dark-theme">

    <header class="header">
        <div class="logo">StreamVerse</div>
        <nav class="nav">
            <ul class="nav-list">
                <li><a href="#home">Home</a></li>
                <li><a href="#filmes">Filmes</a></li>
                <li><a href="#series">Séries</a></li>
                <li><a href="#tv-aberta">TV Aberta</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>
        </nav>
        <div class="header-right">
            <button id="theme-toggle" class="theme-toggle">
                <span class="icon-moon">🌙</span>
                <span class="icon-sun">☀️</span>
            </button>
            <button class="hamburger" aria-label="Menu">
                <span class="bar"></span>
                <span class="bar"></span>
                <span class="bar"></span>
            </button>
        </div>
    </header>

    <main>
        <section id="home" class="section hero-banner">
            <div class="hero-content">
                <h1>Destaques da Semana</h1>
                <p>Descubra os filmes e séries mais populares e aclamados do momento. Sempre atualizado para você.</p>
                <a href="#filmes" class="btn btn-primary">Ver Filmes Agora</a>
            </div>
        </section>
        
        <section id="filmes" class="section">
            <h2>Filmes Populares</h2>
            <div class="card-grid">
                <div class="movie-card">
                    <img src="https://image.tmdb.org/t/p/w500/z6B6j94jM80n5xS14J6R6Vp6Q9g.jpg" alt="Filme 1">
                    <div class="card-info">
                        <h3>O Protetor</h3>
                    </div>
                </div>
                <div class="movie-card">
                    <img src="https://image.tmdb.org/t/p/w500/yW80J7F7m8l1P6TfL92oWd9vKkK.jpg" alt="Filme 2">
                    <div class="card-info">
                        <h3>Oppenheimer</h3>
                    </div>
                </div>
                <div class="movie-card">
                    <img src="https://image.tmdb.org/t/p/w500/t6b7mYy4g2v6fFk4fQ5N9c3yVp5.jpg" alt="Filme 3">
                    <div class="card-info">
                        <h3>Barbie</h3>
                    </div>
                </div>
                <div class="movie-card">
                    <img src="https://image.tmdb.org/t/p/w500/jL3V9kG14X9p3r8eS7oM3M8g8lJ.jpg" alt="Filme 4">
                    <div class="card-info">
                        <h3>Missão Impossível</h3>
                    </div>
                </div>
                <div class="movie-card">
                    <img src="https://image.tmdb.org/t/p/w500/qjSKQp4i6917fW3vXgR64X77Jc9.jpg" alt="Filme 5">
                    <div class="card-info">
                        <h3>John Wick 4</h3>
                    </div>
                </div>
            </div>
        </section>

        <section id="series" class="section">
            <h2>Séries em Alta</h2>
            <div class="card-grid">
                <div class="movie-card">
                    <img src="https://image.tmdb.org/t/p/w500/vGfL3hKz7yPj8G1c8gBf1uC0mO.jpg" alt="Série 1">
                    <div class="card-info">
                        <h3>Loki</h3>
                    </div>
                </div>
                <div class="movie-card">
                    <img src="https://image.tmdb.org/t/p/w500/1X6tK1tB4p7zVz1H9Q6jB5tB4x.jpg" alt="Série 2">
                    <div class="card-info">
                        <h3>The Last of Us</h3>
                    </div>
                </div>
                <div class="movie-card">
                    <img src="https://image.tmdb.org/t/p/w500/xVzJ82K3VpP6L7fC2uB1Qj3Z4Cq.jpg" alt="Série 3">
                    <div class="card-info">
                        <h3>Stranger Things</h3>
                    </div>
                </div>
                <div class="movie-card">
                    <img src="https://image.tmdb.org/t/p/w500/9618K0iGjY81kYwz4nJ3B8yW6Lq.jpg" alt="Série 4">
                    <div class="card-info">
                        <h3>Wandinha</h3>
                    </div>
                </div>
                <div class="movie-card">
                    <img src="https://image.tmdb.org/t/p/w500/1t0E8mJ3bN5sLpS0qJ3fKjKjD8o.jpg" alt="Série 5">
                    <div class="card-info">
                        <h3>The Mandalorian</h3>
                    </div>
                </div>
            </div>
        </section>

        <section id="tv-aberta" class="section">
            <h2>TV Aberta</h2>
            <p>Seção em desenvolvimento. Fique de olho para canais de TV ao vivo!</p>
        </section>
        
        <section id="contato" class="section">
            <h2>Contato</h2>
            <form class="contact-form">
                <input type="text" placeholder="Seu Nome" required>
                <input type="email" placeholder="Seu E-mail" required>
                <textarea placeholder="Sua Mensagem" rows="5" required></textarea>
                <button type="submit" class="btn btn-primary">Enviar Mensagem</button>
            </form>
        </section>
    </main>
    
    <footer class="footer">
        <p>&copy; 2023 YouCine Clone. Todos os direitos reservados.</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const themeToggle = document.getElementById('theme-toggle');
            const body = document.body;
            const hamburger = document.querySelector('.hamburger');
            const nav = document.querySelector('.nav');

            // Checar e aplicar o tema salvo no LocalStorage
            const savedTheme = localStorage.getItem('theme');
            if (savedTheme) {
                body.classList.add(savedTheme);
            } else {
                body.classList.add('dark-theme');
            }

            // Lógica de alternância de tema
            themeToggle.addEventListener('click', () => {
                if (body.classList.contains('dark-theme')) {
                    body.classList.remove('dark-theme');
                    body.classList.add('light-theme');
                    localStorage.setItem('theme', 'light-theme');
                } else {
                    body.classList.remove('light-theme');
                    body.classList.add('dark-theme');
                    localStorage.setItem('theme', 'dark-theme');
                }
            });

            // Lógica do menu hambúrguer para mobile
            hamburger.addEventListener('click', () => {
                nav.classList.toggle('open');
            });

            // Fechar menu ao clicar em um link
            nav.querySelectorAll('a').forEach(link => {
                link.addEventListener('click', () => {
                    nav.classList.remove('open');
                });
            });
        });
    </script>
</body>
</html>
