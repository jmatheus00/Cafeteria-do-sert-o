<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cafeteria - Café do Sertão</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: #2c2c2c;
            line-height: 1.6;
            background: #f5f5f5;
        }

        /* Header com efeito 3D/4D */
        header {
            background: linear-gradient(135deg, rgba(60, 60, 60, 0.95) 0%, rgba(40, 40, 40, 0.95) 100%),
                        url('https://images.unsplash.com/photo-1559056199-641a0ac8b3f4?w=1200&h=500&fit=crop') center/cover;
            color: #e8e8e8;
            text-align: center;
            padding: 80px 20px;
            position: relative;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.5), inset 0 1px 0 rgba(255, 255, 255, 0.1);
            overflow: hidden;
        }

        header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.05) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        header h1 {
            font-size: 2.8em;
            text-shadow: 3px 3px 8px rgba(0, 0, 0, 0.8),
                         6px 6px 16px rgba(0, 0, 0, 0.6);
            letter-spacing: 3px;
            position: relative;
            z-index: 1;
            font-weight: 300;
        }

        /* Seção de boas-vindas */
        .welcome-section {
            background: linear-gradient(180deg, #ffffff 0%, #fafafa 100%);
            text-align: center;
            padding: 60px 20px;
            border-bottom: 1px solid #e0e0e0;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
        }

        .welcome-section h2 {
            font-size: 2em;
            margin-bottom: 15px;
            font-weight: 300;
            color: #3c3c3c;
        }

        .welcome-section p {
            font-size: 1.1em;
            color: #666;
            font-weight: 300;
        }

        /* Seção de menu */
        .menu-section {
            padding: 60px 20px;
            background: linear-gradient(180deg, #f5f5f5 0%, #efefef 100%);
        }

        .menu-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 40px;
        }

        .menu-card {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.12),
                        0 2px 4px rgba(0, 0, 0, 0.08);
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
        }

        .menu-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2),
                        0 5px 10px rgba(0, 0, 0, 0.15);
        }

        .menu-card-header {
            background: linear-gradient(135deg, #4a4a4a 0%, #3c3c3c 100%);
            color: #e8e8e8;
            padding: 30px 20px;
            text-align: center;
            border-bottom: 2px solid #2a2a2a;
        }

        .menu-card-header h3 {
            font-size: 1.6em;
            font-weight: 300;
            letter-spacing: 1px;
        }

        .menu-card-body {
            padding: 30px 20px;
            background: linear-gradient(135deg, #ffffff 0%, #f9f9f9 100%),
                        url('https://images.unsplash.com/photo-1512568400610-62da28bc8a13?w=400&h=300&fit=crop') center/cover;
            background-attachment: fixed;
            position: relative;
        }

        .menu-card-body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.95) 0%, rgba(249, 249, 249, 0.95) 100%);
            pointer-events: none;
        }

        .menu-item {
            background: rgba(255, 255, 255, 0.8);
            margin-bottom: 18px;
            padding: 15px;
            border-radius: 6px;
            border-left: 3px solid #4a4a4a;
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.06);
            position: relative;
            z-index: 1;
            transition: all 0.3s ease;
        }

        .menu-item:hover {
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            transform: translateX(4px);
        }

        .menu-item h4 {
            font-size: 0.95em;
            color: #3c3c3c;
            margin-bottom: 6px;
            font-weight: 500;
        }

        .menu-item span {
            font-weight: 600;
            color: #4a4a4a;
            margin-right: 8px;
        }

        .price {
            color: #666;
            font-weight: 500;
            font-size: 1.05em;
        }

        /* Seção de botão */
        .button-section {
            background: linear-gradient(135deg, rgba(80, 80, 80, 0.95) 0%, rgba(60, 60, 60, 0.95) 100%),
                        url('https://images.unsplash.com/photo-1447933601403-0c6688bcf566?w=1200&h=300&fit=crop') center/cover;
            text-align: center;
            padding: 70px 20px;
            position: relative;
            overflow: hidden;
        }

        .button-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, rgba(80, 80, 80, 0.95) 0%, rgba(60, 60, 60, 0.95) 100%);
            z-index: 0;
        }

        .botao-redondo {
            background: linear-gradient(135deg, #5a5a5a 0%, #4a4a4a 100%);
            color: #e8e8e8;
            border: none;
            border-radius: 50px;
            padding: 16px 50px;
            font-size: 1.05em;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3),
                        inset 0 1px 0 rgba(255, 255, 255, 0.2),
                        0 0 0 0 rgba(255, 255, 255, 0);
            position: relative;
            z-index: 1;
            letter-spacing: 0.5px;
        }

        .botao-redondo:hover {
            background: linear-gradient(135deg, #6a6a6a 0%, #5a5a5a 100%);
            transform: translateY(-3px);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.4),
                        inset 0 1px 0 rgba(255, 255, 255, 0.3),
                        0 0 20px rgba(255, 255, 255, 0.1);
        }

        .botao-redondo:active {
            transform: translateY(-1px);
            box-shadow: 0 6px 14px rgba(0, 0, 0, 0.3),
                        inset 0 1px 0 rgba(255, 255, 255, 0.2);
        }

        /* Footer */
        footer {
            background: linear-gradient(135deg, #3c3c3c 0%, #2a2a2a 100%);
            color: #a8a8a8;
            text-align: center;
            padding: 25px 20px;
            border-top: 1px solid #1a1a1a;
            box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.05);
        }

        footer p {
            font-size: 0.95em;
            font-weight: 300;
            letter-spacing: 0.5px;
        }

        /* Responsividade */
        @media (max-width: 758px) {
            header h1 {
                font-size: 1.8em;
            }

            header {
                padding: 40px 20px;
            }

            .menu-container {
                grid-template-columns: 1fr;
                gap: 30px;
            }

            .menu-card-body {
                background-attachment: scroll;
            }

            .welcome-section {
                padding: 40px 10px;
            }

            .button-section {
                padding: 40px 10px;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>CAFÉ DO SERTÃO</h1>
    </header>

    <section class="welcome-section">
        <h2>Bem-vindo</h2>
        <p>Faça seu pedido</p>
    </section>

    <section class="menu-section">
        <div class="menu-container">
            <!-- Café Preto -->
            <div class="menu-card">
                <div class="menu-card-header">
                    <h3>Café Preto</h3>
                </div>
                <div class="menu-card-body">
                    <div class="menu-item">
                        <div>
                            
                        
                            <section class="button-secion">
        <button class="botao-redondo">pequeno
        150</button>
    </section>
      </div>
                                <section class="button-secion">
        <button class="botao-redondo">medio
        250ml</button>
    
                                <section class="button-secion">
        <button class="botao-redondo">Grande
        400ml</button>

    

            <!-- Café com Leite -->
            <div class="menu-card">
                <div class="menu-card-header">
                    <h3>Café com Leite</h3>
                </div>
                <div class="menu-card-body">
                    <div class="menu-item">
                        <h4><span>Pequeno</span> 150ml</h4>
                        <p class="price">R$ 5,00</p>
                    </div>
                    <div class="menu-item">
                        <h4><span>Médio</span> 250ml</h4>
                        <p class="price">R$ 10,50</p>
                    </div>
                    <div class="menu-item">
                        <h4><span>Grande</span> 400ml</h4>
                        <p class="price">R$ 12,50</p>
                    </div>
                </div>
            </div>

            <!-- Nescafé -->
            <div class="menu-card">
                <div class="menu-card-header">
                    <h3>Nescafé</h3>
                </div>
                <div class="menu-card-body">
                    <div class="menu-item">
                        <h4><span>Pequeno</span> 150ml</h4>
                        <p class="price">R$ 7,50</p>
                    </div>
                    <div class="menu-item">
                        <h4><span>Médio</span> 250ml</h4>
                        <p class="price">R$ 11,00</p>
                    </div>
                    <div class="menu-item">
                        <h4><span>Grande</span> 400ml</h4>
                        <p class="price">R$ 23,00</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="button-section">
        <button class="botao-redondo">Fazer Pedido</button>
    </section>

    <footer>
        <p>&copy; Cafeteria 2026 - Café do Sertão</p>
    </
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cafeteria - Café do Sertão</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: #2c2c2c;
            line-height: 1.6;
            background: #f5f5f5;
        }

        /* Header com efeito 3D/4D */
        header {
            background: linear-gradient(135deg, rgba(60, 60, 60, 0.95) 0%, rgba(40, 40, 40, 0.95) 100%),
                        url('https://unsplash.com') center/cover;
            color: #e8e8e8;
            text-align: center;
            padding: 80px 20px;
            position: relative;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.5), inset 0 1px 0 rgba(255, 255, 255, 0.1);
            overflow: hidden;
        }

        header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.05) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        header h1 {
            font-size: 2.8em;
            text-shadow: 3px 3px 8px rgba(0, 0, 0, 0.8),
                         6px 6px 16px rgba(0, 0, 0, 0.6);
            letter-spacing: 3px;
            position: relative;
            z-index: 1;
            font-weight: 300;
        }

        /* Seção de boas-vindas */
        .welcome-section {
            background: linear-gradient(180deg, #ffffff 0%, #fafafa 100%);
            text-align: center;
            padding: 60px 20px;
            border-bottom: 1px solid #e0e0e0;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
        }

        .welcome-section h2 {
            font-size: 2em;
            margin-bottom: 15px;
            font-weight: 300;
            color: #3c3c3c;
        }

        .welcome-section p {
            font-size: 1.1em;
            color: #666;
            font-weight: 300;
        }

        /* Seção de menu */
        .menu-section {
            padding: 60px 20px;
            background: linear-gradient(180deg, #f5f5f5 0%, #efefef 100%);
        }

        .menu-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 40px;
        }

        .menu-card {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.12),
                        0 2px 4px rgba(0, 0, 0, 0.08);
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
        }

        .menu-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2),
                        0 5px 10px rgba(0, 0, 0, 0.15);
        }

        .menu-card-header {
            background: linear-gradient(135deg, #4a4a4a 0%, #3c3c3c 100%);
            color: #e8e8e8;
            padding: 30px 20px;
            text-align: center;
            border-bottom: 2px solid #2a2a2a;
        }

        .menu-card-header h3 {
            font-size: 1.6em;
            font-weight: 300;
            letter-spacing: 1px;
        }

        .menu-card-body {
            padding: 30px 20px;
            background: linear-gradient(135deg, #ffffff 0%, #f9f9f9 100%),
                        url('https://unsplash.com') center/cover;
            background-attachment: fixed;
            position: relative;
        }

        .menu-card-body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.95) 0%, rgba(249, 249, 249, 0.95) 100%);
            pointer-events: none;
        }

        .menu-item {
            background: rgba(255, 255, 255, 0.8);
            margin-bottom: 18px;
            padding: 15px;
            border-radius: 6px;
            border-left: 3px solid #4a4a4a;
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.06);
            position: relative;
            z-index: 1;
            transition: all 0.3s ease;
        }

        .menu-item:hover {
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            transform: translateX(4px);
        }

        .menu-item h4 {
            font-size: 0.95em;
            color: #3c3c3c;
            margin-bottom: 6px;
            font-weight: 500;
        }

        .menu-item span {
            font-weight: 600;
            color: #4a4a4a;
            margin-right: 8px;
        }

        .price {
            color: #666;
            font-weight: 500;
            font-size: 1.05em;
        }

        /* O SEGREDO ESTÁ AQUI: Mudamos essa parte para separar os botões */
        .button-section {
            background: linear-gradient(135deg, rgba(80, 80, 80, 0.95) 0%, rgba(60, 60, 60, 0.95) 100%),
                        url('https://unsplash.com') center/cover;
            text-align: center;
            padding: 70px 20px;
            position: relative;
            overflow: hidden;

            /* Ativamos o Flexbox para colocar um do lado do outro */
            display: flex; 
            justify-content: center; /* Centraliza eles na tela */
            gap: 20px;               /* IMPORTANTE: Cria o espaço de 20px ENTRE os botões */
            flex-wrap: wrap;         /* Se a tela for pequena (celular), eles vão para baixo organizados */
        }

        .button-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, rgba(80, 80, 80, 0.95) 0%, rgba(60, 60, 60, 0.95) 100%);
            z-index: 0;
        }

        .botao-redondo {
            background: linear-gradient(135deg, #5a5a5a 0%, #4a4a4a 100%);
            color: #e8e8e8;
            border: none;
            border-radius: 50px;
            padding: 16px 50px;
            font-size: 1.05em;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3),
                        inset 0 1px 0 rgba(255, 255, 255, 0.2),
                        0 0 0 0 rgba(255, 255, 255, 0);
            position: relative;
            z-index: 1;
            letter-spacing: 0.5px;
        }

        .botao-redondo:hover {
            background: linear-gradient(135deg, #6a6a6a 0%, #5a5a5a 100%);
            transform: translateY(-3px);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.4),
                        inset 0 1px 0 rgba(255, 255, 255, 0.3),
                        0 0 20px rgba(255, 255, 255, 0.1);
        }

        .botao-redondo:active {
            transform: translateY(-1px);
            box-shadow: 0 6px 14px rgba(0, 0, 0, 0.3),
                        inset 0 1px 0 rgba(255, 255, 255, 0.2);
        }

        /* Footer */
        footer {
            background: linear-gradient(135deg, #3c3c3c 0%, #2a2a2a 100%);
            color: #a8a8a8;
            text-align: center;
            padding: 25px 20px;
            border-top: 1px solid #1a1a1a;
            box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.05);
        }

        footer p {
            font-size: 0.95em;
            font-weight: 300;
            letter-spacing: 0.5px;
        }

        /* Responsividade */
        @media (max-width: 758px) {
            header h1 { font-size: 1.8em; }
            header { padding: 40px 20px; }
            .menu-container { grid-template-columns: 1fr; gap: 30px; }
            .menu-card-body { background-attachment: scroll; }
            .welcome-section { padding: 40px 20px; }
        }
    </style>
</head>
<body>

    <header>
        <h1>Café do Sertão</h1>
    </header>

    <section class="welcome-section">
        <h2>Bem-vindo à nossa cafeteria</h2>
        <p>Os melhores grãos selecionados direto para a sua xícara.</p>
    </section>

    <!-- Exemplo de Menu -->
    <section class="menu-section">
        <div class="menu-container">
            <div class="menu-card">
                <div class="menu-card-header">
                    <h3>                  </div>
                    <div class="menu-item">
                        <h4><span>Grande</span> 400ml</h4>
                        <p class="price">R$ 12,50</p>
                    </div>
                </div>
            </div>

            <!-- Nescafé -->
            <div class="menu-card">
                <div class="menu-card-header">
                    <h3>Nescafé</h3>
                </div>
                <div class="menu-card-body">
                    <div class="menu-item">
                        <h4><span>Pequeno</span> 150ml</h4>
                        <p class="price">R$ 7,50</p>
                    </div>
                    <div class="menu-item">
                        <h4><span>Médio</span> 250ml</h4>
                        <p class="price">R$ 11,00</p>
                    </div>
                    <div class="menu-item">
                        <h4><span>Grande</span> 400ml</h4>
                        <p class="price">R$ 23,00</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="button-section">
        <button class="botao-redondo">Fazer Pedido</button>
    </section>

    <footer>
        <p>&copy; Cafeteria 2026 - Café do Sertão</p>
    </footer>
</body>
</html>
