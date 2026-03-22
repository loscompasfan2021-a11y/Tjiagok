<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GameStore PS4 & PS5 - Los Mejores Videojuegos</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #333;
            min-height: 100vh;
        }

        header {
            background: rgba(0,0,0,0.9);
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            color: #fff;
            font-size: 2rem;
            font-weight: bold;
            text-decoration: none;
        }

        .logo span {
            color: #00ff88;
        }

        .cart {
            background: #00ff88;
            color: #000;
            padding: 0.5rem 1rem;
            border-radius: 25px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s;
        }

        .cart:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(0,255,136,0.4);
        }

        main {
            margin-top: 80px;
            max-width: 1200px;
            margin-left: auto;
            margin-right: auto;
            padding: 2rem;
        }

        .hero {
            text-align: center;
            color: white;
            margin-bottom: 3rem;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        .hero p {
            font-size: 1.2rem;
            opacity: 0.9;
        }

        .filters {
            display: flex;
            gap: 1rem;
            margin-bottom: 2rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .filter-btn {
            background: rgba(255,255,255,0.2);
            color: white;
            border: 2px solid rgba(255,255,255,0.3);
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s;
            backdrop-filter: blur(10px);
        }

        .filter-btn:hover, .filter-btn.active {
            background: #00ff88;
            color: #000;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,255,136,0.4);
        }

        .games-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .game-card {
            background: rgba(255,255,255,0.95);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            transition: all 0.4s ease;
            position: relative;
        }

        .game-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 40px rgba(0,0,0,0.4);
        }

        .game-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .game-info {
            padding: 1.5rem;
        }

        .game-title {
            font-size: 1.3rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            color: #333;
        }

        .game-platforms {
            display: flex;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .platform-tag {
            background: #00ff88;
            color: #000;
            padding: 0.2rem 0.8rem;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .game-price {
            font-size: 1.5rem;
            font-weight: bold;
            color: #e74c3c;
            margin-bottom: 1rem;
        }

        .buy-btn {
            width: 100%;
            background: linear-gradient(45deg, #00ff88, #00cc6a);
            color: #000;
            border: none;
            padding: 1rem;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
        }

        .buy-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 20px rgba(0,255,136,0.5);
        }

        .ps4-only { opacity: 0.6; }
        .ps5-only { opacity: 0.6; }

        footer {
            background: rgba(0,0,0,0.9);
            color: white;
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
        }

        @media (max-width: 768px) {
            .hero h1 { font-size: 2rem; }
            .games-grid { grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <a href="#" class="logo">Game<span>Store</span></a>
            <a href="#" class="cart">🛒 Carrito (0)</a>
        </nav>
    </header>

    <main>
        <div class="hero">
            <h1>🔥 Los 20 Mejores Juegos PS4 & PS5</h1>
            <p>Los títulos mejor valorados de la historia de PlayStation</p>
        </div>

        <div class="filters">
            <button class="filter-btn active" data-filter="all">Todos</button>
            <button class="filter-btn" data-filter="ps4">Solo PS4</button>
            <button class="filter-btn" data-filter="ps5">Solo PS5</button>
            <button class="filter-btn" data-filter="both">Ambas</button>
        </div>

        <div class="games-grid" id="gamesGrid">
            <!-- Los 20 juegos mejor catalogados -->
            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1592938889701-7f87e587e4b7?w=400&h=200&fit=crop" alt="The Last of Us Part II" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">The Last of Us Part II</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS4</span>
                        <span class="platform-tag">PS5</span>
                    </div>
                    <div class="game-price">$49.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1600585154340-be6161a56a0c?w=400&h=200&fit=crop" alt="God of War" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">God of War (2018)</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS4</span>
                        <span class="platform-tag">PS5</span>
                    </div>
                    <div class="game-price">$39.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1577902681093-f6b5533f3e1e?w=400&h=200&fit=crop" alt="Spider-Man" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">Marvel's Spider-Man</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS4</span>
                        <span class="platform-tag">PS5</span>
                    </div>
                    <div class="game-price">$44.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1612240492147-5a4201753e77?w=400&h=200&fit=crop" alt="Horizon Zero Dawn" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">Horizon Zero Dawn</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS4</span>
                        <span class="platform-tag">PS5</span>
                    </div>
                    <div class="game-price">$29.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1604967653359-849b91a8b7d8?w=400&h=200&fit=crop" alt="Ghost of Tsushima" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">Ghost of Tsushima</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS4</span>
                        <span class="platform-tag">PS5</span>
                    </div>
                    <div class="game-price">$49.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1611606069427-8b5f47b60a1f?w=400&h=200&fit=crop" alt="Bloodborne" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">Bloodborne</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS4</span>
                    </div>
                    <div class="game-price">$29.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1572897937538-239e0bd212b1?w=400&h=200&fit=crop" alt="Uncharted 4" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">Uncharted 4: A Thief's End</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS4</span>
                        <span class="platform-tag">PS5</span>
                    </div>
                    <div class="game-price">$24.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1606890658317-7d4e69c64864?w=400&h=200&fit=crop" alt="Ratchet & Clank" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">Ratchet & Clank: Rift Apart</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS5</span>
                    </div>
                    <div class="game-price">$59.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1611747068077-392c35f7a0d0?w=400&h=200&fit=crop" alt="Death Stranding" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">Death Stranding Director's Cut</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS4</span>
                        <span class="platform-tag">PS5</span>
                    </div>
                    <div class="game-price">$39.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1570549717069-33bed2eb6f96?w=400&h=200&fit=crop" alt="Resident Evil 2" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">Resident Evil 2 Remake</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS4</span>
                        <span class="platform-tag">PS5</span>
                    </div>
                    <div class="game-price">$29.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1603354623048-7f6a9621b9d8?w=400&h=200&fit=crop" alt="Elden Ring" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">Elden Ring</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS4</span>
                        <span class="platform-tag">PS5</span>
                    </div>
                    <div class="game-price">$59.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1542751371-adc38448a05e?w=400&h=200&fit=crop" alt="The Witcher 3" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">The Witcher 3: Wild Hunt</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS4</span>
                        <span class="platform-tag">PS5</span>
                    </div>
                    <div class="game-price">$29.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1600585154526-990dced4cb0d?w=400&h=200&fit=crop" alt="Final Fantasy VII Remake" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">Final Fantasy VII Remake</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS4</span>
                        <span class="platform-tag">PS5</span>
                    </div>
                    <div class="game-price">$49.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1615965819542-247898ad9ab6?w=400&h=200&fit=crop" alt="Demon's Souls" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">Demon's Souls</h3>
                    <div class="game-platforms">
                        <span class="platform-tag">PS5</span>
                    </div>
                    <div class="game-price">$69.99</div>
                    <button class="buy-btn">🛒 Comprar Ahora</button>
                </div>
            </div>

            <div class="game-card" data-ps4="true" data-ps5="true">
                <img src="https://images.unsplash.com/photo-1603354623048-7f6a9621b9d8?w=400&h=200&fit=crop" alt="Returnal" class="game-image">
                <div class="game-info">
                    <h3 class="game-title">Returnal</h3>
                    <div class="game-platforms">
                        <span class="platform
