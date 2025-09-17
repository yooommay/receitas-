# receitas-
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Receitas Saudáveis</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #ffffff;
      color: #111111;
      line-height: 1.6;
      margin: 0;
      font-size: 1rem;
      transition: all 0.3s ease;
    }
    header {
      background-color: #004080;
      color: #ffffff;
      padding: 1rem;
      text-align: center;
    }
    nav a {
      color: #ffcc00;
      margin: 0 1rem;
      text-decoration: none;
      font-weight: bold;
    }
    nav a:focus, nav a:hover {
      text-decoration: underline;
    }
    main {
      padding: 2rem;
    }
    article {
      background: #f4f4f4;
      padding: 1.5rem;
      margin-bottom: 1.5rem;
      border-radius: 8px;
    }
    h2 {
      color: #004080;
    }
    footer {
      background-color: #222;
      color: #fff;
      text-align: center;
      padding: 1rem;
    }
    .btn {
      background: #004080;
      color: #fff;
      padding: 0.5rem 1rem;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .btn:hover, .btn:focus {
      background: #003060;
      outline: 2px solid #ffcc00;
    }

    /* Botão de acessibilidade fixo */
    .acessibilidade {
      position: fixed;
      top: 10px;
      right: 10px;
      background: #004080;
      color: white;
      border: none;
      padding: 0.8rem;
      border-radius: 50%;
      cursor: pointer;
      z-index: 1000;
    }
    .acessibilidade:focus {
      outline: 3px solid #ffcc00;
    }

    /* Menu de acessibilidade */
    .painel-acessibilidade {
      position: fixed;
      top: 60px;
      right: 10px;
      background: #fff;
      border: 2px solid #004080;
      border-radius: 8px;
      padding: 1rem;
      display: none;
      z-index: 1000;
    }
    .painel-acessibilidade button {
      display: block;
      width: 100%;
      margin-bottom: 0.5rem;
    }

    /* Modo alto contraste */
    body.alto-contraste {
      background-color: #000;
      color: #fff;
    }
    body.alto-contraste header,
    body.alto-contraste footer {
      background-color: #000;
      color: #ff0;
    }
    body.alto-contraste .btn {
      background: #ff0;
      color: #000;
    }
    body.alto-contraste nav a {
      color: #0ff;
    }
  </style>
</head>
<body>
  <header role="banner">
    <h1>Receitas Saudáveis</h1>
    <nav role="navigation" aria-label="Menu principal">
      <a href="#receita1">Smoothie de Frutas</a>
      <a href="#receita2">Salada Colorida</a>
      <a href="#receita3">Sopa de Abóbora</a>
    </nav>
  </header>

  <!-- Botão de acessibilidade -->
  <button class="acessibilidade" aria-label="Abrir painel de acessibilidade" aria-expanded="false" aria-controls="painelAcessibilidade">
    ♿
  </button>

  <!-- Painel de acessibilidade -->
  <div id="painelAcessibilidade" class="painel-acessibilidade" role="dialog" aria-label="Configurações de acessibilidade">
    <button class="btn" id="aumentarFonte">Aumentar Fonte</button>
    <button class="btn" id="diminuirFonte">Diminuir Fonte</button>
    <button class="btn" id="alternarContraste">Ativar/Desativar Contraste</button>
  </div>

  <main role="main">
    <article id="receita1" aria-labelledby="titulo1">
      <h2 id="titulo1">Smoothie de Frutas</h2>
      <img src="smoothie.jpg" alt="Copo de smoothie de frutas vermelhas" width="300">
      <p>Um smoothie nutritivo feito com morango, banana e aveia. Ideal para começar o dia com energia.</p>
      <button class="btn" aria-label="Ver receita completa de Smoothie de Frutas">Ver Receita</button>
    </article>

    <article id="receita2" aria-labelledby="titulo2">
      <h2 id="titulo2">Salada Colorida</h2>
      <img src="salada.jpg" alt="Salada colorida com legumes frescos" width="300">
      <p>Uma salada leve e refrescante com cenoura, pepino, rúcula e grão-de-bico.</p>
      <button class="btn" aria-label="Ver receita completa de Salada Colorida">Ver Receita</button>
    </article>

    <article id="receita3" aria-labelledby="titulo3">
      <h2 id="titulo3">Sopa de Abóbora</h2>
      <img src="sopa.jpg" alt="Tigela de sopa de abóbora cremosa" width="300">
      <p>Uma sopa cremosa, rica em fibras e perfeita para os dias frios.</p>
      <button class="btn" aria-label="Ver receita completa de Sopa de Abóbora">Ver Receita</button>
    </article>
  </main>

  <footer role="contentinfo">
    <p>&copy; 2025 Receitas Saudáveis | Desenvolvido com acessibilidade em mente</p>
  </footer>

  <script>
    const botaoAcessibilidade = document.querySelector('.acessibilidade');
    const painel = document.getElementById('painelAcessibilidade');
    const aumentarFonte = document.getElementById('aumentarFonte');
    const diminuirFonte = document.getElementById('diminuirFonte');
    const alternarContraste = document.getElementById('alternarContraste');

    let tamanhoFonte = 1; // rem base

    // Abrir/fechar painel
    botaoAcessibilidade.addEventListener('click', () => {
      const expandido = botaoAcessibilidade.getAttribute('aria-expanded') === 'true';
      botaoAcessibilidade.setAttribute('aria-expanded', !expandido);
      painel.style.display = expandido ? 'none' : 'block';
    });

    // Aumentar fonte
    aumentarFonte.addEventListener('click', () => {
      tamanhoFonte += 0.1;
      document.body.style.fontSize = tamanhoFonte + 'rem';
    });

    // Diminuir fonte
    diminuirFonte.addEventListener('click', () => {
      if (tamanhoFonte > 0.7) {
        tamanhoFonte -= 0.1;
        document.body.style.fontSize = tamanhoFonte + 'rem';
      }
    });

    // Alternar contraste
    alternarContraste.addEventListener('click', () => {
      document.body.classList.toggle('alto-contraste');
    });
  </script>
</body>
</html>
