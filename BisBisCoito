<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>bis.bis.coito - Encomendas</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Pacifico&family=Montserrat:wght@400;700&display=swap');
    body {
      font-family: 'Montserrat', sans-serif;
      background-color: #def4f4;
      color: #333;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 1.5rem 1rem 4rem;
      position: relative;
      overflow-x: hidden;
    }
    h1, h2 {
      font-family: 'Pacifico', cursive;
      color: #b96ca0;
    }
    /* Logo wrapper with circle */
    .logo-container {
      background-color: #7ed6d6;
      border-radius: 50%;
      padding: 1.5rem;
      max-width: 200px;
      margin: 0 auto 1rem;
      box-shadow: 0 0 15px rgba(125, 214, 214, 0.7);
      display: flex;
      justify-content: center;
      align-items: center;
      animation: float 3s ease-in-out infinite;
    }
    .logo-container img {
      max-width: 100%;
      height: auto;
    }
    /* Card styles for categories */
    .category-card {
      background: white;
      box-shadow: 0 2px 6px rgb(0 0 0 / 0.1);
      border-radius: 10px;
      padding: 1.15rem 1.25rem 1.8rem;
      margin-bottom: 1.75rem;
      width: 100%;
      max-width: 480px;
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
    }
    .category-card:hover {
      box-shadow: 0 6px 15px rgb(185 108 160 / 0.35);
      transform: translateY(-5px);
    }
    .category-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255,255,254,0.5), transparent);
      transition: 0.5s;
    }
    .category-card:hover::before {
      left: 100%;
    }
    .category-header {
      font-size: 1.75rem;
      margin-bottom: 0.8rem;
      display: flex;
      align-items: center;
      gap: 0.6rem;
      user-select: none;
      cursor: pointer;
      position: relative;
      padding: 0.5rem;
      border-radius: 5px;
      transition: background-color 0.3s;
    }
    .category-header:hover {
      background-color: rgba(185, 108, 160, 0.1);
    }
    .product-item {
      display: flex;
      justify-content: space-between;
      margin-bottom: 0.45rem;
      font-size: 1.05rem;
      padding: 0.5rem;
      border-radius: 5px;
      transition: background-color 0.2s;
    }
    .product-item:hover {
      background-color: rgba(125, 214, 214, 0.1);
    }
    .product-desc {
      font-style: italic;
      font-size: 0.94rem;
      color: #666;
      margin-top: 0.15rem;
      max-width: 90%;
    }
    /* Form inputs styling */
    .input-label {
      font-weight: 700;
      margin-bottom: 0.3rem;
      display: block;
      color: #555;
      position: relative;
      padding-left: 20px;
    }
    .input-label::before {
      content: '🛒';
      position: absolute;
      left: 0;
      top: 0;
    }
    input[type="number"],
    input[type="date"] {
      border: 1.9px solid #b96ca0;
      border-radius: 6px;
      width: 100%;
      padding: 0.5rem 0.75rem;
      font-size: 1rem;
      color: #333;
      outline-offset: 3px;
      margin-bottom: 1rem;
      font-family: 'Montserrat', sans-serif;
      transition: all 0.3s ease;
    }
    input[type="number"]:focus,
    input[type="date"]:focus {
      border-color: #7ed6d6;
      box-shadow: 0 0 10px #7ed6d6b3;
      transform: scale(1.02);
    }
    .submit-btn {
      background-color: #b96ca0;
      color: white;
      font-family: 'Pacifico', cursive;
      font-size: 1.3rem;
      padding: 0.7rem 1.8rem;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(185, 108, 160, 0.5);
      transition: all 0.3s ease;
      user-select: none;
      margin-top: 0.5rem;
      width: 100%;
      max-width: 480px;
      position: relative;
      overflow: hidden;
    }
    .submit-btn:hover {
      background-color: #ca83b1;
      transform: scale(1.05);
      box-shadow: 0 6px 15px rgba(185, 108, 160, 0.7);
    }
    .submit-btn:active {
      transform: scale(0.98);
    }
    .submit-btn::after {
      content: '→';
      position: absolute;
      right: 20px;
      top: 50%;
      transform: translateY(-50%);
      opacity: 0;
      transition: all 0.3s ease;
    }
    .submit-btn:hover::after {
      opacity: 1;
      right: 15px;
    }
    /* Payment info stylization */
    .payment-info {
      margin-top: 1.8rem;
      font-weight: 700;
      font-size: 1.1rem;
      text-align: center;
      color: #7d6ca0;
      max-width: 500px;
      line-height: 1.4;
      user-select: text;
      padding: 1rem;
      background: rgba(255, 255, 255, 0.7);
      border-radius: 10px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    }
    .payment-info strong {
      color: #b96ca0;
    }
    /* Responsive adjustments */
    @media (max-width: 520px) {
      .category-card {
        padding: 1rem 1rem 1.4rem;
      }
      .category-header {
        font-size: 1.5rem;
      }
      .product-item {
        font-size: 1rem;
      }
      .submit-btn {
        font-size: 1.1rem;
      }
    }
    /* Animation */
    @keyframes float {
      0% { transform: translateY(0px); }
      50% { transform: translateY(-10px); }
      100% { transform: translateY(0px); }
    }
    /* Progress bar */
    .progress-container {
      width: 100%;
      max-width: 480px;
      margin-bottom: 1.5rem;
      background: rgba(255,255,255,0.5);
      border-radius: 10px;
      padding: 1rem;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    }
    .progress-bar {
      height: 10px;
      background: #e0e0e0;
      border-radius: 5px;
      overflow: hidden;
    }
    .progress-fill {
      height: 100%;
      background: linear-gradient(90deg, #b96ca0, #7ed6d6);
      width: 0%;
      transition: width 0.5s ease;
    }
    .progress-text {
      text-align: center;
      margin-top: 0.5rem;
      font-weight: bold;
      color: #b96ca0;
    }
    /* Feedback messages */
    .feedback {
      padding: 1rem;
      border-radius: 8px;
      margin: 1rem 0;
      text-align: center;
      font-weight: bold;
      display: none;
    }
    .feedback.success {
      background-color: #d4edda;
      color: #155724;
      border: 1px solid #c3e6cb;
    }
    .feedback.error {
      background-color: #f8d7da;
      color: #721c24;
      border: 1px solid #f5c6cb;
    }
    /* Floating elements */
    .floating-element {
      position: absolute;
      font-size: 2rem;
      opacity: 0;
      z-index: -1;
    }
  </style>
</head>
<body>
  <div class="floating-element">🧁</div>
  <div class="floating-element">🍫</div>
  <div class="floating-element">🍪</div>
  <div class="floating-element">🍓</div>
  <header>
    <div class="logo-container" aria-label="Logo da bis.bis.coito com bolachas de chocolate ao centro e texto rosa arredondado dizendo 'bis.bis.coito quem come quer mais!' num círculo azul claro">
      <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/06e695c1-c037-4acc-992d-947c60195053.png" alt="Logo redondo da bis.bis.coito, círculo azul claro com o texto rosa 'bis.bis.coito quem come quer mais!' ao redor de três bolachas de chocolate com gotas escuras no centro" onerror="this.onerror=null;this.src='https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/8eea03ab-935b-4c93-915e-265cc62d5089.png';" />
    </div>
    <h1 class="text-center text-4xl mb-4 select-text">bis.bis.coito - Encomendas</h1>
    <div class="progress-container">
      <div class="progress-bar">
        <div class="progress-fill" id="progressFill"></div>
      </div>
      <div class="progress-text" id="progressText">Comece a selecionar seus produtos!</div>
    </div>
  </header>
  <main>
    <form id="orderForm" class="w-full max-w-lg" aria-label="Formulário de encomendas da bis.bis.coito">
      <!-- Bolo de Pote -->
      <section class="category-card" aria-labelledby="bolo-pote-header">
        <h2 class="category-header" id="bolo-pote-header" tabindex="0">🧁 BOLO DE POTE</h2>
        <div class="product-list">
          <label class="input-label" for="ninhoMorango">Ninho com Morango - R$ 13,00</label>
          <input type="number" id="ninhoMorango" name="ninhoMorango" min="0" max="30" value="0" aria-describedby="descNinhoMorango" />
          <span id="descNinhoMorango" class="product-desc">Quantidade de bolos de pote de Ninho com Morango</span>
          <label class="input-label" for="abacaxi">Abacaxi - R$ 13,00</label>
          <input type="number" id="abacaxi" name="abacaxi" min="0" max="30" value="0" aria-describedby="descAbacaxi" />
          <span id="descAbacaxi" class="product-desc">Quantidade de bolos de pote sabor Abacaxi</span>
        </div>
      </section>
      <!-- Brownies Recheados -->
      <section class="category-card" aria-labelledby="brownies-header">
        <h2 class="category-header" id="brownies-header" tabindex="0">🍫 BROWNIES RECHEADOS</h2>
        <div class="product-list">
          <label class="input-label" for="brownieDoceLeite">Brownie Doce de leite - R$ 6,00</label>
          <input type="number" id="brownieDoceLeite" name="brownieDoceLeite" min="0" max="40" value="0" aria-describedby="descBrownieDoceLeite" />
          <span id="descBrownieDoceLeite" class="product-desc">Quantidade de brownies recheados com doce de leite</span>
          <label class="input-label" for="brownieBrigadeiro">Brownie Brigadeiro - R$ 6,00</label>
          <input type="number" id="brownieBrigadeiro" name="brownieBrigadeiro" min="0" max="40" value="0" aria-describedby="descBrownieBrigadeiro" />
          <span id="descBrownieBrigadeiro" class="product-desc">Quantidade de brownies recheados com brigadeiro</span>
          <p class="product-desc mt-1 text-center">Delicioso e derrete na boca!</p>
        </div>
      </section>
      <!-- Morango do Amor -->
      <section class="category-card" aria-labelledby="morango-header">
        <h2 class="category-header" id="morango-header" tabindex="0">🍓 MORANGO DO AMOR</h2>
        <div class="product-list">
          <label class="input-label" for="morangoAmor">Morango do Amor - R$ 10,00</label>
          <input type="number" id="morangoAmor" name="morangoAmor" min="0" max="30" value="0" aria-describedby="descMorangoAmor" />
          <span id="descMorangoAmor" class="product-desc">Quantidade de morangos do amor</span>
          <p class="product-desc mt-1 text-center">💖 Delicado, sofisticado e feito com afeto.
Quem prova, se apaixona!</p>
        </div>
      </section>
      <!-- Biscoitos Elizabeth -->
      <section class="category-card" aria-labelledby="biscoitos-header">
        <h2 class="category-header" id="biscoitos-header" tabindex="0">🍪 BISCOITOS ELIZABETH</h2>
        <div class="product-list">
          <label class="input-label" for="biscoito100g">100g - R$ 6,00</label>
          <input type="number" id="biscoito100g" name="biscoito100g" min="0" max="50" value="0" aria-describedby="descBiscoito100g" />
          <span id="descBiscoito100g" class="product-desc">Quantidade de biscoitos Elizabeth 100 gramas</span>
          <label class="input-label" for="biscoito160g">160g - R$ 9,50</label>
          <input type="number" id="biscoito160g" name="biscoito160g" min="0" max="50" value="0" aria-describedby="descBiscoito160g" />
          <span id="descBiscoito160g" class="product-desc">Quantidade de biscoitos Elizabeth 160 gramas</span>
          <label class="input-label" for="biscoito310g">310g - R$ 19,00</label>
          <input type="number" id="biscoito310g" name="biscoito310g" min="0" max="30" value="0" aria-describedby="descBiscoito310g" />
          <span id="descBiscoito310g" class="product-desc">Quantidade de biscoitos Elizabeth 310 gramas</span>
          <label class="input-label" for="biscoito460g">460g - R$ 28,00</label>
          <input type="number" id="biscoito460g" name="biscoito460g" min="0" max="30" value="0" aria-describedby="descBiscoito460g" />
          <span id="descBiscoito460g" class="product-desc">Quantidade de biscoitos Elizabeth 460 gramas</span>
          <label class="input-label" for="biscoito750g">750g - R$ 46,00</label>
          <input type="number" id="biscoito750g" name="biscoito750g" min="0" max="20" value="0" aria-describedby="descBiscoito750g" />
          <span id="descBiscoito750g" class="product-desc">Quantidade de biscoitos Elizabeth 750 gramas</span>
        </div>
      </section>
      <section class="category-card" aria-labelledby="date-header">
        <h2 class="category-header" id="date-header" tabindex="0">📅 Data desejada para entrega</h2>
        <label class="input-label" for="deliveryDate">Escolha a data</label>
        <input type="date" id="deliveryDate" name="deliveryDate" min="" required aria-required="true" />
      </section>
      <div id="feedbackMessage" class="feedback"></div>
      <button type="submit" class="submit-btn" aria-label="Enviar pedido via WhatsApp">Enviar Pedido</button>
      <div class="payment-info" aria-live="polite" aria-atomic="true" aria-relevant="additions">
        <p>Forma de pagamento: <strong>PIX</strong> apenas pelo número: <strong>21 96653-4618</strong></p>
      </div>
    </form>
  </main>
  <script>
    // Set minimum date for datepicker to today
    const dateInput = document.getElementById('deliveryDate');
    const today = new Date().toISOString().split('T')[0];
    dateInput.setAttribute('min', today);
    // Progress tracking
    const progressFill = document.getElementById('progressFill');
    const progressText = document.getElementById('progressText');
    const inputs = document.querySelectorAll('input[type="number"]');
    const dateInputField = document.getElementById('deliveryDate');
    // Feedback message element
    const feedbackMessage = document.getElementById('feedbackMessage');
    // Floating elements
    const floatingElements = document.querySelectorAll('.floating-element');
    // Initialize floating elements
    function initFloatingElements() {
      floatingElements.forEach(el => {
        el.style.left = Math.random() * 100 + 'vw';
        el.style.top = Math.random() * 100 + 'vh';
        el.style.fontSize = (Math.random() * 2 + 1) + 'rem';
        el.style.animation = `float ${Math.random() * 3 + 2}s ease-in-out infinite`;
        el.style.opacity = '0.7';
      });
    }
    // Update progress bar
    function updateProgress() {
      let totalItems = 0;
      let selectedItems = 0;
      inputs.forEach(input => {
        totalItems++;
        if (parseInt(input.value) > 0) {
          selectedItems++;
        }
      });
      // Check if date is selected
      if (dateInputField.value) {
        selectedItems++;
        totalItems++;
      }
      const progress = totalItems > 0 ? (selectedItems / totalItems) * 100 : 0;
      progressFill.style.width = progress + '%';
      if (progress === 0) {
        progressText.textContent = 'Comece a selecionar seus produtos!';
      } else if (progress < 50) {
        progressText.textContent = 'Continue escolhendo seus produtos favoritos!';
      } else if (progress < 100) {
        progressText.textContent = 'Quase lá! Só falta mais um detalhe!';
      } else {
        progressText.textContent = 'Tudo pronto! Clique em "Enviar Pedido"!';
      }
    }
    // Show feedback message
    function showFeedback(message, isSuccess) {
      feedbackMessage.textContent = message;
      feedbackMessage.className = 'feedback ' + (isSuccess ? 'success' : 'error');
      feedbackMessage.style.display = 'block';
      setTimeout(() => {
        feedbackMessage.style.display = 'none';
      }, 3000);
    }
    // Add event listeners to inputs
    inputs.forEach(input => {
      input.addEventListener('input', updateProgress);
    });
    dateInputField.addEventListener('change', updateProgress);
    // Form submission
    const form = document.getElementById('orderForm');
    form.addEventListener('submit', (e) => {
      e.preventDefault();
      // Collect quantities
      const quantities = {
        ninhoMorango: parseInt(form.ninhoMorango.value, 10),
        abacaxi: parseInt(form.abacaxi.value, 10),
        brownieDoceLeite: parseInt(form.brownieDoceLeite.value, 10),
        brownieBrigadeiro: parseInt(form.brownieBrigadeiro.value, 10),
        morangoAmor: parseInt(form.morangoAmor.value, 10),
        biscoito100g: parseInt(form.biscoito100g.value, 10),
        biscoito160g: parseInt(form.biscoito160g.value, 10),
        biscoito310g: parseInt(form.biscoito310g.value, 10),
        biscoito460g: parseInt(form.biscoito460g.value, 10),
        biscoito750g: parseInt(form.biscoito750g.value, 10),
      };
      // Validate if at least one product was ordered
      const totalQuantity = Object.values(quantities).reduce((a, b) => a + b, 0);
      if(totalQuantity === 0) {
        showFeedback('Por favor, selecione pelo menos um item para pedido.', false);
        return;
      }
      // Validate date selection
      const deliveryDate = form.deliveryDate.value;
      if(!deliveryDate) {
        showFeedback('Por favor, selecione a data da encomenda desejada.', false);
        return;
      }
      // Show success message
      showFeedback('Pedido enviado com sucesso! Aguarde o redirecionamento para o WhatsApp.', true);
      // Compose order message for WhatsApp
      let message = `Olá, eu gostaria de fazer um pedido da bis.bis.coito.%0A`;
      message += `Data desejada para entrega: ${deliveryDate}%0A%0A`;
      // Build order details lines for items with quantity > 0
      if(quantities.ninhoMorango > 0) {
        message += `🧁 Bolo de Pote - Ninho com Morango: ${quantities.ninhoMorango} unidade(s) - R$ ${(quantities.ninhoMorango * 13).toFixed(2)}%0A`;
      }
      if(quantities.abacaxi > 0) {
        message += `🧁 Bolo de Pote - Abacaxi: ${quantities.abacaxi} unidade(s) - R$ ${(quantities.abacaxi * 13).toFixed(2)}%0A`;
      }
      if(quantities.brownieDoceLeite > 0) {
        message += `🍫 Brownie Recheado - Doce de leite: ${quantities.brownieDoceLeite} unidade(s) - R$ ${(quantities.brownieDoceLeite * 6).toFixed(2)}%0A`;
      }
      if(quantities.brownieBrigadeiro > 0) {
        message += `🍫 Brownie Recheado - Brigadeiro: ${quantities.brownieBrigadeiro} unidade(s) - R$ ${(quantities.brownieBrigadeiro * 6).toFixed(2)}%0A`;
      }
      if(quantities.morangoAmor > 0) {
        message += `🍓 Morango do Amor: ${quantities.morangoAmor} unidade(s) - R$ ${(quantities.morangoAmor * 10).toFixed(2)}%0A`;
      }
      if(quantities.biscoito100g > 0) {
        message += `🍪 Biscoitos Elizabeth 100g: ${quantities.biscoito100g} unidade(s) - R$ ${(quantities.biscoito100g * 6).toFixed(2)}%0A`;
      }
      if(quantities.biscoito160g > 0) {
        message += `🍪 Biscoitos Elizabeth 160g: ${quantities.biscoito160g} unidade(s) - R$ ${(quantities.biscoito160g * 9.5).toFixed(2)}%0A`;
      }
      if(quantities.biscoito310g > 0) {
        message += `🍪 Biscoitos Elizabeth 310g: ${quantities.biscoito310g} unidade(s) - R$ ${(quantities.biscoito310g * 19).toFixed(2)}%0A`;
      }
      if(quantities.biscoito460g > 0) {
        message += `🍪 Biscoitos Elizabeth 460g: ${quantities.biscoito460g} unidade(s) - R$ ${(quantities.biscoito460g * 28).toFixed(2)}%0A`;
      }
      if(quantities.biscoito750g > 0) {
        message += `🍪 Biscoitos Elizabeth 750g: ${quantities.biscoito750g} unidade(s) - R$ ${(quantities.biscoito750g * 46).toFixed(2)}%0A`;
      }
      message += `%0AForma de pagamento: PIX apenas pelo número 21 96653-4618.`;
      // Open WhatsApp to send message after a delay
      setTimeout(() => {
        const phone = '5521966534618';
        const url = `https://wa.me/${phone}?text=${message}`;
        window.open(url, '_blank');
      }, 2000);
    });
    // Initialize
    document.addEventListener('DOMContentLoaded', () => {
      initFloatingElements();
      updateProgress();
    });
  </script>
</body>
</html>
