<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Институт Белой Магии города Тбилиси</title>
<style>
  html, body {
    margin: 0; padding: 0; height: 100%;
    font-family: Arial, sans-serif;
    color: white;
    overflow-x: hidden;
  }

  /* Фон */
  body::before {
    content: "";
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    background: url('https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=1470&q=80') center/cover no-repeat;
    filter: blur(8px) brightness(0.35);
    z-index: -2;
  }
  body::after {
    content: "";
    position: fixed;
    top:0; left:0;
    width:100%; height:100%;
    background: rgba(0,0,0,0.7);
    z-index: -1;
  }

  /* Навигация */
  .nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    background: rgba(0,0,0,0.85);
    display: flex;
    justify-content: center;
    gap: 30px;
    padding: 15px;
    z-index: 1000;
  }
  .nav a {
    color: gold;
    text-decoration: none;
    font-weight: bold;
  }

  /* Заголовок */
  .header {
    margin-top: 80px;
    text-align: center;
    padding: 120px 20px 60px;
  }
  .header h1 { color: gold; margin-bottom: 8px; }
  .btn {
    background: gold;
    border: none;
    padding: 14px 30px;
    font-size: 18px;
    border-radius: 5px;
    cursor: pointer;
    color: #111;
    transition: background 0.3s;
  }
  .btn:hover { background: #e6c200; }

  /* Секции */
  .section {
    max-width: 1100px;
    margin: 0 auto 80px;
    padding: 0 20px;
    text-align: center;
  }
  .section h2 { color: gold; margin-bottom: 25px; }
  .section p { max-width: 700px; margin: 0 auto 20px; font-size: 18px; line-height: 1.5; }

  /* Карточки */
  .cards { display: flex; justify-content: center; gap: 20px; flex-wrap: wrap; }
  .card {
    background: rgba(0,0,0,0.6);
    border-radius: 10px;
    padding: 20px;
    width: 260px;
    box-shadow: 0 0 15px rgba(255,215,0,0.3);
    text-align: center;
    cursor: pointer;
  }
  .mage img {
    width: 100%; height: 260px; object-fit: cover; border-radius: 10px;
  }
  .mage h3 { color: gold; margin: 12px 0 5px; }
  .mage p { color: #ddd; font-style: italic; }

  /* Звезды */
  .stars { color: gold; font-size: 20px; margin-bottom: 12px; }

  /* Модальное окно */
  .modal {
    display: none;
    position: fixed;
    top:0; left:0;
    width: 100%; height: 100%;
    background: rgba(0,0,0,0.85);
    justify-content: center;
    align-items: center;
    z-index: 2000;
  }
  .modal.active { display: flex; }
  .modal-content {
    background: #111;
    padding: 30px 25px;
    border-radius: 10px;
    width: 360px;
    position: relative;
    color: white;
    max-height: 90vh;
    overflow-y: auto;
  }
  .modal-content h3 { margin-top: 0; margin-bottom: 20px; text-align: center; }
  .modal-content p { text-align: justify; }
  .modal-content input, .modal-content textarea {
    width: 100%; padding: 12px 10px; margin-bottom: 15px; border-radius: 5px; border: none; font-size: 16px;
  }
  .modal-content textarea { resize: vertical; min-height: 80px; }
  .modal-content button {
    width: 100%; background: gold; border: none; padding: 14px; font-size: 18px; border-radius: 5px; cursor: pointer; color: #111; transition: background 0.3s;
  }
  .modal-content button:hover { background: #e6c200; }
  .close {
    position: absolute; top: 15px; right: 20px;
    font-size: 24px; cursor: pointer; color: #aaa; transition: color 0.2s;
  }
  .close:hover { color: white; }
</style>
</head>
<body>

<!-- Навигация -->
<div class="nav">
  <a href="#about">О нас</a>
  <a href="#services">Услуги</a>
  <a href="#mages">Маги</a>
  <a href="#reviews">Отзывы</a>
  <a href="#contact">Контакты</a>
</div>

<!-- Заголовок -->
<div class="header">
  <h1>Институт Белой Магии города Тбилиси</h1>
  <p>Помощь через свет и энергию</p>
  <button class="btn" id="openModalBtn">Связаться с нами</button>
</div>

<!-- О нас -->
<div class="section" id="about">
  <h2>О нас</h2>
  <p>
    Мы — закрытое сообщество практиков белой магии, посвятивших свою жизнь помощи людям в самых сложных ситуациях.  
    К нам обращаются, когда обычные методы не работают и нужна глубокая работа с энергией и судьбой.  
    За годы практики мы помогли сотням людей восстановить отношения, избавиться от негатива и вернуть контроль над жизнью.  
    Каждый случай — уникален. Мы подходим индивидуально, используя только безопасные и эффективные практики.  
    С нами вы получите не просто консультацию, а реальную помощь и поддержку.  
    Почувствуйте, как меняется ваша жизнь к лучшему вместе с нами.
  </p>
</div>

<!-- Услуги -->
<div class="section" id="services">
  <h2>Услуги</h2>
  <div class="cards">
    <div class="card">
      <h3>Защита</h3>
      <p>Создаём энергетические барьеры и защищаем от негатива, предотвращаем дурное влияние извне.</p>
    </div>
    <div class="card">
      <h3>Очищение</h3>
      <p>Помогаем очищать ауру, восстанавливать внутреннюю гармонию и возвращать жизненную энергию.</p>
    </div>
    <div class="card">
      <h3>Диагностика</h3>
      <p>Определяем энергетические блоки и причины проблем, подбираем индивидуальные решения.</p>
    </div>
    <div class="card">
      <h3>Поддержка</h3>
      <p>Консультации и сопровождение в духовном развитии, помощь на пути к гармоничной жизни.</p>
    </div>
  </div>
</div>

<!-- Маги -->
<div class="section" id="mages">
  <h2>Наши маги</h2>
  <div class="cards">

    <div class="card mage" data-name="Святозар" data-desc="Святозар обучался магическим практикам в Тбилиси более 30 лет. Он специализируется на защите и энергетических барьерах, помогая сотням людей справляться с негативной энергией. Его методы уникальны, безопасны и проверены десятилетиями. Святозар также проводит личные консультации и обучает новых магов. Он известен своей доброжелательностью и глубоким пониманием человеческой души. С ним легко работать и доверять." >
      <img src="https://files.catbox.moe/ek4njr.jpg" alt="Святозар" />
      <h3>Святозар</h3>
      <p>Мастер защиты и энергетики</p>
    </div>

    <div class="card mage" data-name="Михаил" data-desc="Михаил обучался более 30 лет в стенах Иерусалима, изучая древние практики целительства и энергетической диагностики. Он помогает людям восстанавливать внутреннюю гармонию, улучшать отношения и находить путь к себе. Михаил известен своей терпимостью и чуткостью, всегда внимательно выслушивает клиента. Он обучает технике безопасного очищения ауры и проведения духовных практик. Его подход индивидуален и максимально эффективен." >
      <img src="https://files.catbox.moe/h5x0id.jpg" alt="Михаил" />
      <h3>Михаил</h3>
      <p>Целитель и духовный наставник</p>
    </div>

    <div class="card mage" data-name="Георгий" data-desc="Георгий посвятил 35 лет изучению диагностики судьбы и духовного развития в различных центрах Европы. Он мастерски определяет энергетические блоки, помогает находить правильное решение проблем. Его методики безопасны и проверены временем. Георгий консультирует по личным и семейным вопросам, обучает правильной гармонизации энергии. Он известен своей мудростью и внимательностью, что делает каждую консультацию результативной и комфортной." >
      <img src="https://files.catbox.moe/qf5o11.jpg" alt="Георгий" />
      <h3>Георгий</h3>
      <p>Диагност судьбы</p>
    </div>

  </div>
</div>

<!-- Отзывы -->
<div class="section" id="reviews">
  <h2>Отзывы</h2>
  <div class="cards">

    <div class="card">
      <h3>Анна</h3>
      <div class="stars">★★★★★</div>
      <p>У меня была проблема с мужем, Михаил решил её очень быстро и эффективно.</p>
    </div>

    <div class="card">
      <h3>Игорь</h3>
      <div class="stars">★★★★★</div>
      <p>После работы со Святозаром жизнь стала гармоничнее и спокойнее.</p>
    </div>

    <div class="card">
      <h3>Марина</h3>
      <div class="stars">★★★★☆</div>
      <p>Чувствовала сильный негатив, после чистки стало легче и светлее.</p>
    </div>

    <div class="card">
      <h3>Олег</h3>
      <div class="stars">★★★★★</div>
      <p>Георгий помог разобраться в сложной ситуации и найти правильный путь.</p>
    </div>

  </div>
</div>

<!-- Контакты -->
<div class="section" id="contact">
  <h2>Контакты</h2>
  <button class="btn" id="openModalBtn2">Оставить заявку</button>
</div>

<!-- Локация -->
<div class="section" id="location">
  <h2>Наша локация</h2>
  <p>
    Наш Институт Белой Магии расположен в живописном монастыре <strong>Вардзия</strong> в Грузии — уникальном историческом комплексе, высеченном в скалах.  
    Это место излучает особую энергетику и способствует духовной гармонии.  
    Здесь наши маги проводят практики, консультации и обучение, обеспечивая атмосферу безопасности и внутреннего покоя.  
    Локация идеально подходит для работы с энергией, очищения ауры и медитаций.  
    Мы приглашаем вас посетить нас и лично почувствовать магию этого удивительного места.
  </p>
  <p><strong>Адрес:</strong> Монастырь Вардзия, Тбилиси, Грузия</p>
</div>

<!-- Модальное окно -->
<div class="modal" id="modal">
  <div class="modal-content" id="modalContent">
    <span class="close" id="closeModalBtn">&times;</span>
    <h3 id="modalTitle">Связаться с нами</h3>
    <form id="contactForm">
      <input type="text" placeholder="ФИО" name="fio" required />
      <input type="email" placeholder="Email" name="email" required />
      <input type="tel" placeholder="Номер телефона" name="phone" required />
      <input type="text" placeholder="Страна" name="country" required />
      <textarea placeholder="Опишите вашу проблему" name="problem" required></textarea>
      <button type="submit" class="btn">Отправить</button>
    </form>
    <p id="mageDesc" style="display:none;"></p>
  </div>
</div>

<script>
  const modal = document.getElementById('modal');
  const modalTitle = document.getElementById('modalTitle');
  const mageDesc = document.getElementById('mageDesc');
  const openModalBtn = document.getElementById('openModalBtn');
  const openModalBtn2 = document.getElementById('openModalBtn2');
  const closeModalBtn = document.getElementById('closeModalBtn');
  const contactForm = document.getElementById('contactForm');

  // Открытие формы
  function openFormModal() {
    modal.classList.add('active');
    contactForm.style.display = 'block';
    mageDesc.style.display = 'none';
    modalTitle.textContent = 'Связаться с нами';
  }
  openModalBtn.addEventListener('click', openFormModal);
  openModalBtn2.addEventListener('click', openFormModal);

  // Закрытие
  function closeModal() {
    modal.classList.remove('active');
  }
  closeModalBtn.addEventListener('click', closeModal);
  window.addEventListener('click', (e) => { if (e.target === modal) closeModal(); });

  contactForm.addEventListener('submit', (e) => {
    e.preventDefault();
    alert('Спасибо за заявку! Мы свяжемся с вами в ближайшее время.');
    contactForm.reset();
    closeModal();
  });

  // Описание магов
  const mageCards = document.querySelectorAll('.mage');
  mageCards.forEach(card => {
    card.addEventListener('click', () => {
      const name = card.dataset.name;
      const desc = card.dataset.desc;
      modal.classList.add('active');
      contactForm.style.display = 'none';
      mageDesc.style.display = 'block';
      modalTitle.textContent = name;
      mageDesc.textContent = desc;
    });
  });
</script>

</body>
</html>
