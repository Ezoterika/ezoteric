<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Институт Белой Магии г. Тбилиси</title>
<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #fdfcfb;
    color: #333;
    line-height: 1.6;
}

/* Шапка */
.header {
    background: linear-gradient(to right, #ffffff, #e8f0ff);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 80px 20px;
}

.header h1 {
    font-size: 48px;
    color: #222;
    margin-bottom: 10px;
}

.header p {
    font-size: 20px;
    margin-bottom: 20px;
}

.btn {
    padding: 14px 30px;
    background: gold;
    border: none;
    cursor: pointer;
    font-size: 18px;
    border-radius: 5px;
    transition: 0.3s;
}

.btn:hover {
    background: #e6c200;
}

/* Блоки информации */
.section {
    padding: 60px 20px;
    max-width: 1200px;
    margin: 0 auto;
}

.section h2 {
    font-size: 36px;
    color: #222;
    margin-bottom: 20px;
    text-align: center;
}

.section p {
    font-size: 18px;
    margin-bottom: 20px;
    text-align: center;
}

/* Карточки преимуществ */
.cards {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    background: #fff;
    padding: 25px;
    width: 300px;
    border-radius: 12px;
    box-shadow: 0 5px 20px rgba(0,0,0,0.08);
    text-align: center;
}

.card h3 {
    font-size: 22px;
    margin-bottom: 10px;
}

.card p {
    font-size: 16px;
}

/* Подвал */
.footer {
    background: #222;
    color: #fff;
    text-align: center;
    padding: 25px;
    margin-top: 40px;
}

/* Модальное окно */
.modal {
    display: none; /* Скрыто по умолчанию */
    position: fixed;
    z-index: 1000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0,0,0,0.6);
}

.modal-content {
    background-color: #fff;
    margin: 10% auto;
    padding: 30px;
    border-radius: 10px;
    max-width: 500px;
    text-align: left;
    position: relative;
}

.close {
    color: #aaa;
    position: absolute;
    top: 15px;
    right: 20px;
    font-size: 28px;
    font-weight: bold;
    cursor: pointer;
}

.close:hover {
    color: #000;
}

.modal-content h2 {
    text-align: center;
    margin-bottom: 20px;
}

.modal-content input, .modal-content textarea {
    width: 100%;
    padding: 10px;
    margin-bottom: 15px;
    border-radius: 5px;
    border: 1px solid #ccc;
    font-size: 16px;
}

.modal-content button {
    width: 100%;
    padding: 12px;
    background: gold;
    border: none;
    font-size: 18px;
    border-radius: 5px;
    cursor: pointer;
}

.modal-content button:hover {
    background: #e6c200;
}
</style>
</head>
<body>

<!-- Главная шапка -->
<div class="header">
    <h1>Институт Белой Магии г. Тбилиси</h1>
    <p>Общество эзотериков, которое помогает людям с помощью белой магии</p>
    <button class="btn" id="openModalBtn">Связаться с нами</button>
</div>

<!-- О институте -->
<div class="section">
    <h2>Кто мы</h2>
    <p>
        Мы — сообщество профессиональных эзотериков, объединённых Институтом Белой Магии г. Тбилиси. 
        Наша цель — помогать людям с гармонизацией жизни, защитой от негативной энергии и раскрытием личного потенциала через белую магию.
    </p>
</div>

<!-- Преимущества -->
<div class="section">
    <h2>Чем мы помогаем</h2>
    <div class="cards">
        <div class="card">
            <h3>Защита</h3>
            <p>Создаём энергетические барьеры и защищаем от негатива.</p>
        </div>
        <div class="card">
            <h3>Диагностика</h3>
            <p>Определяем энергетические блоки и причины проблем.</p>
        </div>
        <div class="card">
            <h3>Очищение</h3>
            <p>Помогаем очищать ауру и восстанавливать внутреннюю гармонию.</p>
        </div>
        <div class="card">
            <h3>Поддержка</h3>
            <p>Консультации и сопровождение в духовном развитии.</p>
        </div>
    </div>
</div>

<!-- Призыв к действию -->
<div class="section">
    <h2>Присоединяйтесь к нашему обществу</h2>
    <p>Мы проводим регулярные встречи и практики. С нами вы научитесь гармонизировать жизнь и использовать силу белой магии на благо себе и другим.</p>
    <button class="btn" id="openModalBtn2">Записаться на консультацию</button>
</div>

<!-- Подвал -->
<div class="footer">
    <p>© Институт Белой Магии г. Тбилиси | Все права защищены</p>
</div>

<!-- Модальное окно -->
<div id="contactModal" class="modal">
  <div class="modal-content">
    <span class="close" id="closeModal">&times;</span>
    <h2>Связаться с нами</h2>
    <form>
        <input type="text" name="fio" placeholder="ФИО" required>
        <input type="number" name="birth" placeholder="Год рождения" required>
        <textarea name="problem" placeholder="Опишите вашу проблему" rows="4" required></textarea>
        <input type="tel" name="phone" placeholder="Номер телефона" required>
        <button type="submit">Отправить</button>
    </form>
  </div>
</div>

<script>
// Открытие модального окна
const modal = document.getElementById("contactModal");
const openBtn = document.getElementById("openModalBtn");
const openBtn2 = document.getElementById("openModalBtn2");
const closeBtn = document.getElementById("closeModal");

openBtn.onclick = function() {
    modal.style.display = "block";
}
openBtn2.onclick = function() {
    modal.style.display = "block";
}

// Закрытие модального окна
closeBtn.onclick = function() {
    modal.style.display = "none";
}

// Закрытие при клике вне окна
window.onclick = function(event) {
    if (event.target == modal) {
        modal.style.display = "none";
    }
}
</script>

</body>
</html>
