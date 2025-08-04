<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Biografia do Professor</title>
<style>
    :root {
    --bg: #fffde9;
    --primary: #e1b53a;
    --active: #ffe082;
    --card: #fff9c4;
    --border: #ffe082;
    --text: #3e3e20;
    --form-bg: #fffbe7;
    --form-header: #fff8b0;
    --scrollbar: #ffe082;
    --scrollbar-thumb: #e1b53a;
    --form-label: #584800;
    }
    
    body {
    background: var(--bg);
    color: var(--text);
    margin: 0;
    min-height: 100vh;
    font-family: 'Montserrat', 'Segoe UI', Arial, sans-serif;
    transition: 0.3s, color 0.3s; 
    }

    /* Layout principal: biografia à esquerda, carrossel à direita, formulário embaixo */
    .main-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;
    width: 100vw;
    box-sizing: border-box;
    padding: 32px 0 0 0;
    gap: 30px;
    background: var(--bg);
    }

    .top-content {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: flex-start;
    width: 100%;
    gap: 40px;
    max-width: 1080px;
    }

    .biography-box {
    background: var(--card);
    border: 2px solid var(--border);
    border-radius: 22px;
    width: 370px;
    min-width: 240px;
    box-shadow: 0 4px 18px 0 rgba(231,181,58,0.12);
    color: var(--text);
    padding: 36px 26px 28px 26px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    }

    .biography-box h2 {
    color: var(--primary);
    border-bottom: 2px solid var(--border);
    margin-top: 0;
    margin-bottom: 20px;
    font-size: 1.85em;
    font-weight: 700;
    padding-bottom: 9px;
    }

    .biography-box p {
    font-size: 1.10em;
    line-height: 1.7;
    margin-bottom: 18px;
    }

    .speak-btn {
    background: var(--primary);
    color: var(--text);
    border: none;
    border-radius: 22px;
    padding: 10px 28px;
    font-size: 1em;
    font-weight: bold;
    margin-top: 10px;
    cursor: pointer;
    transition: 0.2s;
    box-shadow: 0 2px 7px 0 rgba(231,181,58,0.12);
    }

    .speak-btn:hover, .speak-btn:focus {
    background: var(--active);
    outline: none;
    }

    .carousel-box {
    background: var(--card);
    border: 2px solid var(--border);
    border-radius: 22px;
    box-shadow: 0 4px 18px 0 rgba(231,181,58,0.10);
    padding: 24px 18px 18px 18px;
    width: 340px;
    min-width: 220px;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 0;
    }

    .carousel-container {
    position: relative;
    width: 290px;
    height: 180px;
    overflow: hidden;
    border-radius: 15px;
    background: var(--form-bg);
    margin-bottom: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    }

    .carousel-images {
    display: flex;
    width: 100%;
    height: 100%;
    transition: transform 0.5s cubic-bezier(.4,0,.2,1);
    }

    .carousel-images img {
    min-width: 100%;
    height: 100%;
    object-fit: contain;
    background: var(--form-bg);
    display: block;
    border-radius: 15px;
    }

    .carousel-nav {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: var(--primary);
    color: var(--text);
    border: none;
    padding: 9px 14px;
    cursor: pointer;
    border-radius: 50%;
    font-size: 1.15em;
    transition: 0.2s, transform 0.1s;
    z-index: 2;
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0.92;
    }

    .carousel-nav.prev { left: 6px; }
    .carousel-nav.next { right: 6px; }
    .carousel-nav:hover, .carousel-nav:focus {
    background: var(--active);
    transform: scale(1.10) translateY(-50%);
    outline: none;
    }

    .carousel-dots {
    margin-top: 6px;
    display: flex;
    gap: 7px;
    justify-content: center;
    width: 100%;
    }

    .dot {
    width: 11px;
    height: 11px;
    background: var(--border);
    border-radius: 50%;
    cursor: pointer;
    border: 1.2px solid var(--primary);
    transition: 0.3s, transform 0.3s;
    }

    .dot.active {
    background: var(--primary);
    transform: scale(1.16);
    }

    /* Formulário História */
    .form-historia-section {
    width: 100%;
    display: flex;
    justify-content: center;
    margin-top: 16px;
    margin-bottom: 20px;
    }

    .form-historia {
    background: var(--form-bg);
    box-shadow: 0 2px 18px 0 rgba(231,181,58,0.12);
    border-radius: 18px;
    padding: 28px 24px 22px 24px;
    max-width: 780px;
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 17px;
    border: 2px solid var(--primary);
    color: var(--text);
    }

    .form-historia legend {
    font-size: 1.23em;
    font-weight: 700;
    color: var(--form-label);
    
    background: var(--form-header);
    border-radius: 10px;
    padding: 7px 18px;
    margin-bottom: 14px;
    border: 1.5px solid var(--border);
    width: fit-content;
    box-shadow: 0 1px 8px 0 rgba(231,181,58,0.07);
    letter-spacing: 0.5px;
    }

    .form-historia label {
    font-size: 1.11em;
    font-weight: 600;
    margin-bottom: 6px;
    color: var(--form-label);
    }

    .form-historia input,
    .form-historia textarea {
    width: 100%;
    padding: 10px 12px;
    border-radius: 8px;
    border: 1.5px solid var(--primary);
    background: #fff;
    font-size: 1em;
    color: var(--text);
    margin-bottom: 7px;
    font-family: inherit;
    transition: border 0.18s;
    resize: vertical;
    min-height: 36px;
    }

    .form-historia textarea {
    min-height: 60px;
    max-height: 180px;
    }

    .form-historia input:focus,
    .form-historia textarea:focus {
    outline: none;
    border-color: #c7a100;
    }

    .form-historia button {
    margin-top: 16px;
    background: var(--primary);
    color: #fff;
    border: none;
    border-radius: 8px;
    padding: 11px 0 11px 0;
    font-size: 1.12em;
    font-weight: bold;
    cursor: pointer;
    transition: 0.18s;
    box-shadow: 0 2px 7px 0 rgba(231,181,58,0.13);
    }

    .form-historia button:hover,
    .form-historia button:focus {
    background: #c7a100;
    outline: none;
    }

    .form-historia .form-msg {
    margin-top: 12px;
    color: #33691e;
    font-size: 1.08em;
    font-weight: 600;
    display: none;
    }

    /* Barra de rolagem amarela só na main-content */
    .main-content {
    overflow-y: auto;
    height: 100vh;
    scrollbar-width: thin;
    scrollbar-color: var(--scrollbar-thumb) var(--scrollbar);
    }

    .main-content::-webkit-scrollbar {
    width: 13px;
    background: var(--scrollbar);
    }

    .main-content::-webkit-scrollbar-thumb {
    background: var(--scrollbar-thumb);
    border-radius: 7px;
    }

    @media (max-width: 1020px) {
    .top-content {
        flex-direction: column;
        align-items: center;
        gap: 22px;
    }

    .biography-box, .carousel-box {
        width: 95vw;
        max-width: 600px;
    }
    }

    @media (max-width: 650px) {
    .biography-box, .carousel-box, .form-historia {
        padding: 14px 2vw 12px 2vw;
        min-width: unset;
        width: 98vw;
        max-width: 98vw;
    }

    .carousel-container { height: 140px; width: 92vw; max-width: 320px; }
    .form-historia { padding: 10px 1vw 10px 1vw; }
    }

</style>
</head>
<body>
<div class="main-content">
    <div class="top-content">
    <div class="biography-box" id="biografia">
        <h2>Biografia do Professor</h2>
        <p>Professor Antônio Timóteo da Silva Gervasi tem cinquenta e quatro anos. Desde criança, ele gostava de História e decidiu que queria ser professor.</p>
        <p>Depois de muita dedicação e estudo, formou-se em História, Geografia e Pedagogia na Faculdade de Paranaguá, UNESPAR. Começou a dar aulas com vinte e dois anos.</p>
        <p>Um dos desafios enfrentados em sala é a falta de comprometimento e educação dos alunos. Ele tenta resolver isso com diálogo, mas às vezes adota uma postura mais séria.</p>
        <p>Em dois mil e vinte e um, começou a dar aulas no Colégio Instituto.</p>
        <button type="button" class="speak-btn" id="lerTudo" aria-label="Ler Biografia e Fotos">🔊 Ler Biografia e Fotos</button>
    </div>

    <div class="carousel-box">
        <div class="carousel-container" aria-label="Carrossel de conteudo historico" role="region" tabindex="0">
        <div class="carousel-images" id="carouselImgs" aria-live="polite">
            <img src="legal.webp" alt="Guerra dos canudos" />
            <img src="D.pedrovelho.jpg" alt="D.pedro2 idoso" />
            <img src="sei.webp" alt="Martinho Lutero" />
        </div>

        <button class="carousel-nav prev" aria-label="Foto anterior" tabindex="0">&lt;</button>
        <button class="carousel-nav next" aria-label="Próxima foto" tabindex="0">&gt;</button>
        </div>
        <div class="carousel-dots" aria-label="Navegação do carrossel"></div>
    </div>
    </div>

    <!-- Formulário de História -->
    <section class="form-historia-section">
    <form class="form-historia" id="formHistoria" autocomplete="off">
        <legend>Compartilhe sua experiência ou curiosidade sobre História</legend>
        <label for="nome">Seu nome:</label>
        <input type="text" id="nome" name="nome" maxlength="50" required placeholder="Digite seu nome">

        <label for="historia">Conte sua experiência, opinião ou curiosidade sobre História.<br>
        Exemplos: O que você acha importante na matéria? Qual tema você tem mais interesse? Tem alguma dúvida ou sugestão?</label>
        <textarea id="historia" name="historia" maxlength="500" required placeholder="Escreva aqui sua mensagem sobre História..."></textarea>

        <button type="submit">Enviar</button>
        <div class="form-msg" id="formMsg"></div>
    </form>
    </section>
</div>
<script>
    // Carrossel automático e controlável //
    const carouselImagesContainer = document.querySelector('.carousel-images');
    const images = document.querySelectorAll('.carousel-images img');
    const prevButton = document.querySelector('.carousel-nav.prev');
    const nextButton = document.querySelector('.carousel-nav.next');
    const dotsContainer = document.querySelector('.carousel-dots');
    let currentSlide = 0;
    const totalSlides = images.length;
    let intervalId;
    const slideIntervalTime = 3500;

    function showSlide(index) {
    if (index >= totalSlides) currentSlide = 0;
    else if (index < 0) currentSlide = totalSlides - 1;
    else currentSlide = index;
      carouselImagesContainer.style.transform = `translateX(${-currentSlide * 100}%)`;
    updateDots();
    images.forEach((img, i) => img.setAttribute('aria-hidden', i !== currentSlide));
    }

    function nextSlide() { showSlide(currentSlide + 1); }
    function prevSlide() { showSlide(currentSlide - 1); }
    function startCarousel() {
    stopCarousel();
    intervalId = setInterval(nextSlide, slideIntervalTime);
    }

    function stopCarousel() { clearInterval(intervalId); }
    function createDots() {
    dotsContainer.innerHTML = '';
    for (let i = 0; i < totalSlides; i++) {
        const dot = document.createElement('span');
        dot.classList.add('dot');
        dot.setAttribute('role', 'button');
        dot.setAttribute('aria-label', `Ir para foto ${i + 1}`);
        dot.setAttribute('tabindex', '0');
        dot.addEventListener('click', () => { showSlide(i); stopCarousel(); });
        dot.addEventListener('keydown', (e) => {
        if (e.key === 'Enter' || e.key === ' ') { showSlide(i); stopCarousel(); }
        });

        dotsContainer.appendChild(dot);
    }

    updateDots();
    }

    function updateDots() {
    const dots = document.querySelectorAll('.dot');
    dots.forEach((dot, i) => dot.classList.toggle('active', i === currentSlide));
    }

    prevButton.addEventListener('click', () => { prevSlide(); stopCarousel(); });
    nextButton.addEventListener('click', () => { nextSlide(); stopCarousel(); });
    document.querySelector('.carousel-container').addEventListener('keydown', (e) => {
    if (e.key === 'ArrowLeft') { prevSlide(); stopCarousel(); }
    if (e.key === 'ArrowRight') { nextSlide(); stopCarousel(); }
    if (e.key === ' ') { stopCarousel(); }
    });
    createDots();
    showSlide(0);
    startCarousel();

    // Leitor de tela //
    function speakText(text) {
    if (!window.speechSynthesis) return;
    window.speechSynthesis.cancel();
    const utter = new window.SpeechSynthesisUtterance(text);
    utter.lang = 'pt-BR';
    utter.rate = 1.05;
    window.speechSynthesis.speak(utter);
    }

    document.getElementById('lerTudo').addEventListener('click', () => {
    let texto = '';
    texto += document.querySelector('.biography-box h2').innerText + '. ';
    document.querySelectorAll('.biography-box p').forEach(p => { texto += p.innerText + ' '; });
    texto += 'Fotos: ';
    images.forEach((img, i) => { texto += `Foto ${i + 1}: ${img.alt}. `; });
    speakText(texto);
    });

    // Formulário de História (envio simulado) //
    const formHistoria = document.getElementById('formHistoria');
    const formMsg = document.getElementById('formMsg');
    formHistoria.addEventListener('submit', function(e) {
    e.preventDefault();
    const nome = formHistoria.nome.value.trim();
    const historia = formHistoria.historia.value.trim();
    if (nome.length < 2) {
        formMsg.textContent = "Por favor, digite um nome válido.";
        formMsg.style.display = "block";
        return;
    }

    if (historia.length < 5) {
        formMsg.textContent = "Por favor, escreva uma mensagem maior.";
        formMsg.style.display = "block";
        return;
    }

    formMsg.textContent = "História enviada com sucesso! Obrigado por compartilhar.";
    formMsg.style.display = "block";
    formHistoria.reset();
    setTimeout(() => { formMsg.style.display = "none"; }, 3200);
    });

</script>

<!-- VLibras Plugin -->
<div vw class="enabled">
    <div vw-access-button class="active"></div>
    <div vw-plugin-wrapper>
    <div class="vw-plugin-top-wrapper"></div>
    </div>
</div>

<script src="https://vlibras.gov.br/app/vlibras-plugin.js"></script>
<script>
    new window.VLibras.Widget('https://vlibras.gov.br/app');
</script>
</body>
</html># teste
