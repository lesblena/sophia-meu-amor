<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Três Meses Que Nos Vimos</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=Roboto:wght@300;400&display=swap" rel="stylesheet">
  <style>
    /* Configuração do Corpo */
    body {
      margin: 0;
      padding: 0;
      font-family: 'Roboto', sans-serif;
      background: linear-gradient(135deg, #1a1f71, #373b98, #5b67d7);
      background-size: 200% 200%;
      animation: backgroundMove 10s ease infinite;
      color: #fff;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      text-align: center;
    }

    @keyframes backgroundMove {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    h1 {
      font-family: 'Playfair Display', serif;
      font-size: 2.5rem;
      margin: 10px 0;
    }

    /* Contêiner de Poemas */
    .poem-container {
      width: 80%;
      max-width: 800px;
      margin: 20px auto;
      padding: 20px;
      background: rgba(255, 255, 255, 0.1);
      border-radius: 15px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
      font-family: 'Playfair Display', serif;
      font-size: 1.5rem;
      line-height: 2;
      text-align: justify;
      transition: opacity 0.5s ease;
    }

    /* Botões */
    .navigation-buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
      margin-top: 20px;
    }

    .navigation-buttons button {
      padding: 10px 20px;
      font-size: 1rem;
      font-family: 'Roboto', sans-serif;
      color: #fff;
      background: linear-gradient(90deg, #00f2ff, #a1ffce);
      border: none;
      border-radius: 5px;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    .navigation-buttons button:hover {
      transform: translateY(-3px);
      box-shadow: 0 6px 15px rgba(0, 0, 0, 0.5);
    }

    footer {
      margin-top: 20px;
      font-size: 1rem;
      color: rgba(255, 255, 255, 0.8);
    }
  </style>
</head>
<body>
  <h1>Três Meses Que Nos Vimos</h1>

  <!-- Contêiner de Poemas -->
  <div class="poem-container" id="poem-container">
    <p id="poem"></p>
  </div>

  <!-- Botões de Navegação -->
  <div class="navigation-buttons">
    <button id="prev-btn">Anterior</button>
    <button id="next-btn">Próximo</button>
  </div>

  <footer>Feito com amor por Milena para Sophia 💖</footer>

  <script>
    const poems = [
      "Sophia, o universo nasceu quando nossos olhares se cruzaram pela primeira vez. Cada momento ao seu lado é como explorar uma galáxia nova.",
      "Entre mapas ao vivo e trilhas inesperadas, nossos caminhos se encontraram. Quem diria que o caos do destino seria tão perfeito?",
      "Sophia, sua beleza transcende qualquer definição. Seu sorriso é a força gravitacional que mantém meu universo estável.",
      "Se o Big Bang criou o mundo, seu sorriso recriou o meu. Cada segundo com você é uma explosão de felicidade e paz.",
      "Nosso primeiro beijo foi o mais doce caos que já experimentei. Foi o momento em que descobri que o amor tem som, gosto e brilho.",
      "Sophia, desde que te vi, minha vida tem sido guiada por trilhas feitas de estrelas. Você é a luz que ilumina cada passo meu.",
      "Se estamos juntas, até o silêncio se transforma em poesia. Você é a sinfonia mais bela que já ouvi.",
      "Me apaixonei não só por você, mas por tudo o que você representa: força, coragem e um coração repleto de amor.",
      "Sophia, você é como uma supernova: uma explosão de beleza, mistério e força. Com você, minha vida brilha como nunca antes."
    ];

    let currentIndex = 0;

    const poemContainer = document.getElementById("poem-container");
    const poemText = document.getElementById("poem");
    const prevBtn = document.getElementById("prev-btn");
    const nextBtn = document.getElementById("next-btn");

    function displayPoem(index) {
      poemContainer.style.opacity = 0;
      setTimeout(() => {
        poemText.textContent = poems[index];
        poemContainer.style.opacity = 1;
      }, 300);
    }

    prevBtn.addEventListener("click", () => {
      currentIndex = (currentIndex - 1 + poems.length) % poems.length;
      displayPoem(currentIndex);
    });

    nextBtn.addEventListener("click", () => {
      currentIndex = (currentIndex + 1) % poems.length;
      displayPoem(currentIndex);
    });

    // Inicializa o primeiro poema
    displayPoem(currentIndex);
  </script>
</body>
</html>
