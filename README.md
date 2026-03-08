<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>С 8 марта любимая мама</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=SF+Pro+Display:wght@300;400;600;700&family=Playfair+Display:ital,wght@0,400;0,700;1,400&display=swap');

* { margin: 0; padding: 0; box-sizing: border-box; }

:root {
  --dark-bg: rgba(10,0,21,0.95);
  --glass-bg: rgba(255,255,255,0.08);
  --glass-border: rgba(255,255,255,0.15);
  --glass-glow: rgba(255,255,255,0.03);
  --blur: blur(32px);
  --text-primary: rgba(255,255,255,0.95);
  --text-secondary: rgba(255,255,255,0.65);
  --accent-pink: rgba(255,107,157,0.6);
  --accent-purple: rgba(156,39,176,0.5);
}

body {
  min-height: 100vh;
  font-family: -apple-system, 'SF Pro Display', 'Playfair Display', sans-serif;
  overflow-x: hidden;
  background: radial-gradient(ellipse at top, #0a0015 0%, #1a0533 30%, #2d0a3a 60%, #3d0b6b 100%);
  background-attachment: fixed;
  position: relative;
}

body::before {
  content: '';
  position: fixed; top: 0; left: 0; right: 0; bottom: 0;
  background: 
    radial-gradient(circle at 20% 80%, rgba(120,119,198,0.3) 0%, transparent 50%),
    radial-gradient(circle at 80% 20%, rgba(255,119,198,0.3) 0%, transparent 50%),
    radial-gradient(circle at 40% 40%, rgba(120,219,255,0.2) 0%, transparent 50%);
  z-index: -1;
  animation: nebulaShift 20s ease-in-out infinite;
}

@keyframes nebulaShift {
  0%, 100% { opacity: 1; transform: scale(1) rotate(0deg); }
  50% { opacity: 0.8; transform: scale(1.1) rotate(180deg); }
}

/* Floating orbs */
.orbs {
  position: fixed; inset: 0; pointer-events: none; z-index: 0;
}
.orb {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle, var(--accent-pink) 0%, transparent 70%);
  animation: floatOrb linear infinite;
}
@keyframes floatOrb {
  0% { transform: translateY(100vh) scale(0); opacity: 0; }
  10% { opacity: 0.8; transform: translateY(80vh) scale(1); }
  90% { opacity: 0.4; }
  100% { transform: translateY(-20vh) scale(0.6); opacity: 0; }
}

#main-page, #card-page { min-height: 100vh; position: relative; z-index: 1; }
#card-page { display: none; }

.header {
  text-align: center;
  padding: 80px 20px 50px;
  animation: fadeDown 1.2s cubic-bezier(0.34,1.56,0.64,1) forwards;
}
@keyframes fadeDown {
  from { opacity: 0; transform: translateY(-40px); }
  to { opacity: 1; transform: translateY(0); }
}

.header-badge {
  display: inline-block;
  padding: 10px 28px;
  background: var(--glass-bg);
  border: 1px solid var(--glass-border);
  backdrop-filter: var(--blur);
  border-radius: 50px;
  color: var(--text-secondary);
  font-size: 14px;
  letter-spacing: 4px;
  text-transform: uppercase;
  margin-bottom: 24px;
  box-shadow: 0 8px 32px var(--glass-glow);
}

.header h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.5rem, 7vw, 4.5rem);
  font-weight: 700;
  background: linear-gradient(135deg, #ffb3d1 0%, #ff6b9d 50%, #f48fb1 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  line-height: 1.1;
  text-shadow: 0 0 40px rgba(255,107,157,0.5);
  margin-bottom: 16px;
}

.header h1 span { 
  font-style: italic; 
  background: linear-gradient(135deg, #fff 0%, #ffb3d1 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.subtitle {
  font-size: 1.2rem;
  color: var(--text-secondary);
  font-weight: 300;
  letter-spacing: 1.5px;
  backdrop-filter: blur(10px);
}

.divider {
  width: 100px; height: 3px;
  background: linear-gradient(90deg, transparent, var(--accent-pink), transparent);
  margin: 30px auto;
  border-radius: 2px;
  box-shadow: 0 0 20px var(--accent-pink);
}

.cards-intro {
  text-align: center;
  color: var(--text-secondary);
  font-size: 1rem;
  margin: 40px 0 50px;
  letter-spacing: 2px;
  animation: fadeInUp 1.5s ease forwards;
}

@keyframes fadeInUp {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}

.cards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
  padding: 0 30px 80px;
  max-width: 1200px;
  margin: 0 auto;
}

.card {
  position: relative;
  background: linear-gradient(145deg, var(--glass-bg), rgba(255,255,255,0.03));
  border: 1px solid var(--glass-border);
  backdrop-filter: var(--blur);
  border-radius: 32px;
  padding: 40px 32px;
  cursor: pointer;
  overflow: hidden;
  transition: all 0.5s cubic-bezier(0.34,1.56,0.64,1);
  box-shadow: 
    0 20px 60px rgba(0,0,0,0.4),
    inset 0 1px 0 rgba(255,255,255,0.1);
}

.card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--accent-pink), transparent);
  box-shadow: 0 0 20px var(--accent-pink);
}

.card::after {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse 30% 30% at 30% 20%, rgba(255,255,255,0.1), transparent 50%);
  opacity: 0;
  transition: opacity 0.4s ease;
}

.card:hover {
  transform: translateY(-15px) scale(1.03);
  box-shadow: 
    0 40px 100px rgba(0,0,0,0.6),
    0 0 40px var(--accent-pink),
    inset 0 1px 0 rgba(255,255,255,0.2);
}
.card:hover::after { opacity: 1; }

.card-emoji {
  font-size: 3.5rem;
  margin-bottom: 20px;
  display: block;
  filter: drop-shadow(0 0 20px currentColor);
  animation: emojiFloat 3s ease-in-out infinite;
}

@keyframes emojiFloat {
  0%, 100% { transform: translateY(0) rotate(0deg); }
  50% { transform: translateY(-8px) rotate(5deg); }
}

.card-title {
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--text-primary);
  margin-bottom: 12px;
  text-shadow: 0 2px 10px rgba(0,0,0,0.5);
}

.card-preview {
  font-size: 0.95rem;
  color: var(--text-secondary);
  line-height: 1.7;
  margin-bottom: 24px;
}

.card-btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 12px 28px;
  background: linear-gradient(135deg, rgba(255,255,255,0.15), rgba(255,255,255,0.05));
  border: 1px solid var(--glass-border);
  border-radius: 50px;
  color: var(--text-primary);
  font-size: 0.9rem;
  letter-spacing: 1px;
  backdrop-filter: blur(20px);
  transition: all 0.3s ease;
}

.card:hover .card-btn {
  background: linear-gradient(135deg, rgba(255,255,255,0.25), rgba(255,255,255,0.1));
  transform: translateX(8px);
  box-shadow: 0 5px 20px rgba(255,107,157,0.3);
}

/* Modal */
.modal-overlay {
  display: none;
  position: fixed; inset: 0;
  z-index: 100;
  background: rgba(10,0,21,0.9);
  backdrop-filter: blur(12px);
  align-items: center;
  justify-content: center;
  padding: 30px;
  animation: fadeOverlay 0.4s ease;
}

.modal-overlay.active { display: flex; }

@keyframes fadeOverlay { from { opacity: 0; } to { opacity: 1; } }

.modal {
  position: relative;
  background: linear-gradient(145deg, rgba(255,255,255,0.12), rgba(255,255,255,0.02));
  border: 1px solid rgba(255,255,255,0.2);
  backdrop-filter: blur(48px);
  border-radius: 40px;
  padding: 60px 50px;
  max-width: 600px;
  width: 100%;
  text-align: center;
  box-shadow: 
    0 50px 120px rgba(0,0,0,0.7),
    inset 0 1px 0 rgba(255,255,255,0.2);
  animation: modalSlideIn 0.6s cubic-bezier(0.34,1.56,0.64,1) forwards;
}

@keyframes modalSlideIn {
  from { opacity: 0; transform: scale(0.7) translateY(50px); }
  to { opacity: 1; transform: scale(1) translateY(0); }
}

.modal-emoji { 
  font-size: 5rem; 
  margin-bottom: 30px;
  filter: drop-shadow(0 0 40px currentColor);
  animation: bounceGlow 2s ease-in-out infinite;
}

@keyframes bounceGlow {
  0%, 100% { transform: translateY(0) scale(1); filter: drop-shadow(0 0 40px currentColor); }
  50% { transform: translateY(-20px) scale(1.1); filter: drop-shadow(0 0 60px currentColor); }
}

.modal h2 {
  font-family: 'Playfair Display', serif;
  font-size: 2.2rem;
  background: linear-gradient(135deg, #ffb3d1, #ff6b9d);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 25px;
  text-shadow: 0 0 30px rgba(255,107,157,0.5);
}

.modal p {
  font-size: 1.1rem;
  line-height: 1.85;
  color: var(--text-primary);
  font-weight: 300;
  max-width: 500px;
  margin: 0 auto 35px;
}

.name-highlight {
  background: linear-gradient(135deg, #ffb3d1, #ff6b9d);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-family: 'Playfair Display', serif;
  font-style: italic;
  font-weight: 600;
}

.modal-close {
  padding: 16px 40px;
  background: linear-gradient(135deg, rgba(255,255,255,0.2), rgba(255,255,255,0.08));
  border: 1px solid rgba(255,255,255,0.3);
  border-radius: 50px;
  color: var(--text-primary);
  font-size: 1rem;
  cursor: pointer;
  backdrop-filter: blur(20px);
  letter-spacing: 1px;
  transition: all 0.3s ease;
  font-weight: 500;
}

.modal-close:hover {
  background: linear-gradient(135deg, rgba(255,255,255,0.3), rgba(255,255,255,0.15));
  box-shadow: 0 10px 40px rgba(255,107,157,0.4);
  transform: scale(1.05);
}

.footer {
  text-align: center;
  padding: 40px;
  color: var(--text-secondary);
  font-size: 0.85rem;
  letter-spacing: 3px;
  text-shadow: 0 2px 10px rgba(0,0,0,0.8);
}

@media (max-width: 600px) {
  .cards-grid { grid-template-columns: 1fr; gap: 20px; padding: 0 20px 60px; }
  .modal { padding: 40px 30px; }
  .header h1 { font-size: 2.8rem; }
}
</style>
</head>
<body>
<div class="orbs" id="orbs"></div>

<div id="main-page">
  <header class="header">
    <div class="header-badge">✦ 8 МАРТА ✦</div>
    <h1>С праздником,<br><span>любимая мама!</span></h1>
    <div class="divider"></div>
    <p class="subtitle">Виктория Ефимова — лучшая мама на свете 💗</p>
  </header>

  <p class="cards-intro">✨ Выбери карточку с поздравлением ✨</p>

  <div class="cards-grid">
    <div class="card" onclick="openModal(0)">
      <span class="card-emoji">🌸</span>
      <div class="card-title">Нежное поздравление</div>
      <p class="card-preview">Слова любви и благодарности от сердца</p>
      <div class="card-btn">Открыть <span>→</span></div>
    </div>
    <div class="card" onclick="openModal(1)">
      <span class="card-emoji">👑</span>
      <div class="card-title">Ты — Королева</div>
      <p class="card-preview">Комплименты самой прекрасной маме</p>
      <div class="card-btn">Открыть <span>→</span></div>
    </div>
    <div class="card" onclick="openModal(2)">
      <span class="card-emoji">💫</span>
      <div class="card-title">Благодарность</div>
      <p class="card-preview">За всё тепло и заботу каждого дня</p>
      <div class="card-btn">Открыть <span>→</span></div>
    </div>
    <div class="card" onclick="openModal(3)">
      <span class="card-emoji">🌹</span>
      <div class="card-title">Весеннее тепло</div>
      <p class="card-preview">Желания счастья и радости в праздник</p>
      <div class="card-btn">Открыть <span>→</span></div>
    </div>
    <div class="card" onclick="openModal(4)">
      <span class="card-emoji">🦋</span>
      <div class="card-title">Мой кумир</div>
      <p class="card-preview">Вдохновение и пример для подражания</p>
      <div class="card-btn">Открыть <span>→</span></div>
    </div>
    <div class="card" onclick="openModal(5)">
      <span class="card-emoji">💝</span>
      <div class="card-title">Навсегда люблю</div>
      <p class="card-preview">Признание в вечной любви мамочке</p>
      <div class="card-btn">Открыть <span>→</span></div>
    </div>
  </div>

  <footer class="footer">С ЛЮБОВЬЮ ОТ СЕРДЦА ✦ 8 МАРТА 2026</footer>
</div>

<!-- Modal (JavaScript ниже) -->
<div class="modal-overlay" id="modal-overlay">
  <div class="modal">
    <span class="modal-emoji" id="modal-emoji"></span>
    <h2 id="modal-title"></h2>
    <p id="modal-text"></p>
    <button class="modal-close" onclick="closeModal()">✨ Закрыть</button>
  </div>
</div>

<script>
const cards = [
  {
    emoji: "🌸", title: "С 8 Марта, мамочка!",
    text: `Дорогая <span class="name-highlight">Виктория</span>, ты — наш домашний очаг и нежность. Твоя улыбка согревает, а забота защищает. Пусть этот день подарит тебе океан счастья! 💕`
  },
  {
    emoji: "👑", title: "Ты — настоящая Королева!",
    text: `<span class="name-highlight">Виктория</span> — имя победительницы! Ты побеждаешь всё: усталость, заботы, трудности. Оставаясь самой красивой и сильной. 👑✨`
  },
  {
    emoji: "💫", title: "Спасибо за всё, мама",
    text: `За бессонные ночи и тихие утра, вкусные завтраки и мудрые советы. <span class="name-highlight">Виктория</span>, ты — мой самый важный человек в мире. 💫❤️`
  },
  {
    emoji: "🌹", title: "Пусть расцветает весна!",
    text: `Весна празднует твой день, <span class="name-highlight">Виктория</span>! Пусть принесёт лёгкость, счастье, здоровье и тепло любимых. 🌹🌷💖`
  },
  {
    emoji: "🦋", title: "Ты — моё вдохновение",
    text: `<span class="name-highlight">Виктория</span>, ты учишь меня силой примера: любить, не сдаваться, оставаться собой. Ты — моя гордость и ориентир! 🦋✨`
  },
  {
    emoji: "💝", title: "Люблю тебя бесконечно!",
    text: `<span class="name-highlight">Виктория</span>, ты — самый дорогой человек. Люблю за заботу, силу, красоту души. С праздником, любимая мама! ❤️💝`
  }
];

function openModal(i) {
  const c = cards[i];
  document.getElementById('modal-emoji').textContent = c.emoji;
  document.getElementById('modal-title').textContent = c.title;
  document.getElementById('modal-text').innerHTML = c.text;
  document.getElementById('modal-overlay').style.display = 'flex';
}

function closeModal() {
  document.getElementById('modal-overlay').style.display = 'none';
}

// Floating orbs
function createOrbs() {
  const container = document.getElementById('orbs');
  for(let i = 0; i < 12; i++) {
    const orb = document.createElement('div');
    orb.className = 'orb';
    orb.style.cssText = `
      width: ${20 + Math.random() * 40}px;
      height: ${20 + Math.random() * 40}px;
      left: ${Math.random() * 100}%;
      animation-duration: ${15 + Math.random() * 20}s;
      animation-delay: ${Math.random() * 10}s;
      background: radial-gradient(circle, ${['#ff6b9d',' #c084fc',' #67e8f9'][Math.floor(Math.random()*3)]} 0%, transparent 70%);
    `;
    container.appendChild(orb);
  }
}

createOrbs();
setInterval(createOrbs, 15000);
</script>
</body>
</html>
