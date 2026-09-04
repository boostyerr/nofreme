
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>NOFRAME — сайты, которые замечают</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap');

:root {
    --black: #0a0a0a;
    --white: #f3f0e8;
    --gray: #a6a39b;
    --line: #292929;
    --accent: #d9ff3f;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    background: var(--black);
    color: var(--white);
    font-family: Inter, Arial, sans-serif;
    overflow-x: hidden;
}

a {
    color: inherit;
    text-decoration: none;
}

.container {
    width: min(92%, 1250px);
    margin: auto;
}

/* CURSOR */

.cursor {
    position: fixed;
    width: 14px;
    height: 14px;
    background: var(--accent);
    border-radius: 50%;
    pointer-events: none;
    z-index: 9999;
    transform: translate(-50%, -50%);
    mix-blend-mode: difference;
}

/* HEADER */

header {
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 1000;
    padding: 22px 0;
    mix-blend-mode: normal;
}

.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo {
    font-size: 22px;
    font-weight: 900;
    letter-spacing: -1px;
}

.logo span {
    color: var(--accent);
}

.menu {
    display: flex;
    gap: 28px;
    color: #aaa;
    font-size: 14px;
}

.menu a:hover {
    color: var(--white);
}

.contact-btn {
    border: 1px solid #555;
    padding: 10px 17px;
    border-radius: 50px;
    font-size: 13px;
    transition: .25s;
}

.contact-btn:hover {
    background: var(--accent);
    color: #000;
    border-color: var(--accent);
}

/* HERO */

.hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    position: relative;
    overflow: hidden;
}

.hero:before {
    content: "";
    position: absolute;
    width: 600px;
    height: 600px;
    background: var(--accent);
    filter: blur(180px);
    opacity: .08;
    right: -250px;
    top: 20%;
}

.hero-content {
    padding-top: 70px;
}

.small-title {
    color: var(--accent);
    font-size: 13px;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 25px;
}

.hero h1 {
    font-size: clamp(55px, 9vw, 125px);
    line-height: .83;
    letter-spacing: -7px;
    max-width: 1100px;
    text-transform: uppercase;
}

.hero h1 .outline {
    color: transparent;
    -webkit-text-stroke: 1px var(--white);
}

.hero-description {
    max-width: 570px;
    color: var(--gray);
    font-size: 18px;
    line-height: 1.6;
    margin-top: 45px;
}

.hero-bottom {
    margin-top: 60px;
    display: flex;
    align-items: center;
    gap: 30px;
}

.big-button {
    display: inline-flex;
    padding: 17px 25px;
    background: var(--accent);
    color: #000;
    font-weight: 800;
    border-radius: 50px;
    transition: .3s;
}

.big-button:hover {
    transform: scale(1.05);
}

.scroll {
    color: #777;
    font-size: 13px;
}

/* MARQUEE */

.marquee {
    border-top: 1px solid var(--line);
    border-bottom: 1px solid var(--line);
    overflow: hidden;
    white-space: nowrap;
    padding: 18px 0;
}

.marquee-inner {
    display: inline-block;
    animation: marquee 18s linear infinite;
    font-size: 13px;
    letter-spacing: 3px;
    color: #777;
}

.marquee span {
    margin: 0 30px;
    color: var(--accent);
}

@keyframes marquee {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
}

/* INTRO */

.intro {
    padding: 150px 0;
}

.intro-text {
    font-size: clamp(32px, 5vw, 70px);
    line-height: 1.05;
    letter-spacing: -3px;
    max-width: 1100px;
}

.intro-text span {
    color: #444;
}

/* WORK */

.work {
    padding: 100px 0;
}

.section-top {
    display: flex;
    justify-content: space-between;
    align-items: end;
    margin-bottom: 60px;
}

.section-title {
    font-size: 65px;
    letter-spacing: -4px;
}

.section-label {
    color: var(--accent);
    font-size: 12px;
    letter-spacing: 2px;
}

.projects {
    display: grid;
    gap: 25px;
}

.project {
    min-height: 500px;
    border: 1px solid var(--line);
    position: relative;
    overflow: hidden;
    padding: 35px;
    display: flex;
    align-items: end;
    transition: .4s;
}

.project:hover {
    border-color: #555;
    transform: translateY(-5px);
}

.project:nth-child(1) {
    background:
        linear-gradient(120deg, #222, #111),
        radial-gradient(circle, #d9ff3f, transparent);
}

.project:nth-child(2) {
    background:
        linear-gradient(120deg, #171717, #242424);
}

.project:nth-child(3) {
    background:
        linear-gradient(120deg, #282828, #0d0d0d);
}

.project-content {
    position: relative;
    z-index: 2;
}

.project-number {
    font-size: 13px;
    color: var(--accent);
    margin-bottom: 15px;
}

.project h3 {
    font-size: clamp(40px, 6vw, 80px);
    letter-spacing: -4px;
    line-height: .9;
}

.project p {
    color: #aaa;
    margin-top: 15px;
}

.project-tag {
    position: absolute;
    top: 30px;
    right: 30px;
    border: 1px solid #555;
    border-radius: 50px;
    padding: 8px 13px;
    font-size: 11px;
}

/* SERVICES */

.services {
    padding: 120px 0;
}

.service {
    border-top: 1px solid var(--line);
    padding: 35px 0;
    display: grid;
    grid-template-columns: 80px 1fr 2fr 100px;
    align-items: center;
    gap: 20px;
    transition: .3s;
}

.service:last-child {
    border-bottom: 1px solid var(--line);
}

.service:hover {
    padding-left: 15px;
}

.service-number {
    color: var(--accent);
    font-size: 13px;
}

.service h3 {
    font-size: 28px;
}

.service p {
    color: #888;
    max-width: 500px;
}

.arrow {
    font-size: 30px;
    text-align: right;
}

/* DIFFERENCE */

.difference {
    background: var(--white);
    color: #0a0a0a;
    padding: 130px 0;
}

.difference .section-label {
    color: #555;
}

.compare {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1px;
    background: #bbb;
    margin-top: 60px;
}

.compare-box {
    background: var(--white);
    padding: 50px;
    min-height: 300px;
}

.compare-box.bad {
    background: #ddd9d0;
}

.compare-label {
    font-size: 12px;
    letter-spacing: 2px;
    margin-bottom: 35px;
}

.compare-box h3 {
    font-size: 45px;
    letter-spacing: -2px;
    margin-bottom: 20px;
}

.compare-box p {
    color: #555;
    max-width: 450px;
}

/* PROCESS */

.process {
    padding: 130px 0;
}

.process-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
    margin-top: 60px;
}

.step {
    border-left: 1px solid var(--line);
    padding: 20px;
}

.step-number {
    color: var(--accent);
    font-size: 13px;
    margin-bottom: 60px;
}

.step h3 {
    font-size: 22px;
    margin-bottom: 15px;
}

.step p {
    color: #888;
}

/* PRICING */

.pricing {
    padding: 100px 0;
}

.price-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 15px;
    margin-top: 60px;
}

.price-card {
    border: 1px solid var(--line);
    padding: 35px;
    min-height: 450px;
    display: flex;
    flex-direction: column;
}

.price-card.featured {
    background: var(--accent);
    color: #000;
}

.price-card h3 {
    font-size: 25px;
}

.price {
    font-size: 45px;
    font-weight: 800;
    margin: 30px 0;
    letter-spacing: -2px;
}

.price-card ul {
    list-style: none;
    color: #999;
}

.price-card.featured ul {
    color: #333;
}

.price-card li {
    margin: 12px 0;
}

.price-card li:before {
    content: "— ";
}

.price-button {
    margin-top: auto;
    padding: 14px;
    border: 1px solid #444;
    text-align: center;
    border-radius: 50px;
}

.featured .price-button {
    background: #000;
    color: white;
    border-color: #000;
}

/* CTA */

.cta {
    padding: 160px 0;
    text-align: center;
}

.cta h2 {
    font-size: clamp(55px, 9vw, 120px);
    line-height: .85;
    letter-spacing: -6px;
    text-transform: uppercase;
}

.cta h2 span {
    color: var(--accent);
}

.cta p {
    color: #888;
    max-width: 550px;
    margin: 35px auto;
}

/* CONTACT */

.contact {
    border-top: 1px solid var(--line);
    padding: 100px 0;
}

.contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 70px;
}

.contact h2 {
    font-size: 55px;
    letter-spacing: -3px;
}

.contact-left p {
    color: #888;
    margin-top: 25px;
    max-width: 450px;
}

form {
    display: flex;
    flex-direction: column;
    gap: 12px;
}

input,
textarea {
    background: transparent;
    border: 1px solid #333;
    color: white;
    padding: 17px;
    font: inherit;
    outline: none;
}

input:focus,
textarea:focus {
    border-color: var(--accent);
}

textarea {
    height: 130px;
    resize: vertical;
}

form button {
    background: var(--accent);
    border: none;
    padding: 17px;
    font-weight: 800;
    cursor: pointer;
}

/* FOOTER */

footer {
    border-top: 1px solid var(--line);
    padding: 30px 0;
    color: #666;
}

.footer {
    display: flex;
    justify-content: space-between;
}

/* MOBILE */

@media(max-width: 800px) {

    .menu {
        display: none;
    }

    .cursor {
        display: none;
    }

    .hero h1 {
        letter-spacing: -4px;
    }

    .section-title {
        font-size: 45px;
    }

    .service {
        grid-template-columns: 40px 1fr 30px;
    }

    .service p {
        grid-column: 2 / 3;
    }

    .process-grid,
    .price-grid {
        grid-template-columns: 1fr;
    }

    .compare,
    .contact-grid {
        grid-template-columns: 1fr;
    }

    .compare-box {
        min-height: 250px;
    }

    .cta h2 {
        letter-spacing: -4px;
    }

    .footer {
        flex-direction: column;
        gap: 10px;
    }
}

</style>
</head>

<body>

<div class="cursor" id="cursor"></div>


<header>
<div class="container header">

<div class="logo">
NO<span>FRAME</span>
</div>

<div class="menu">
<a href="#work">Работы</a>
<a href="#services">Услуги</a>
<a href="#prices">Стоимость</a>
</div>

<a href="#contact" class="contact-btn">
Обсудить проект
</a>

</div>
</header>


<!-- HERO -->

<section class="hero">

<div class="container hero-content">

<div class="small-title">
01 / Digital studio
</div>

<h1>
Сайт
<br>
который
<br>
<span class="outline">замечают.</span>
</h1>

<p class="hero-description">
Мы создаём сайты для бизнеса, которому недостаточно
просто «быть в интернете». Дизайн, структура и разработка
работают вместе, чтобы превращать внимание в клиентов.
</p>

<div class="hero-bottom">

<a href="#contact" class="big-button">
Начать проект →
</a>

<div class="scroll">
↓ Листай ниже
</div>

</div>

</div>

</section>


<!-- MARQUEE -->

<div class="marquee">

<div class="marquee-inner">

DESIGN <span>✦</span>
DEVELOPMENT <span>✦</span>
BRANDING <span>✦</span>
LANDING PAGES <span>✦</span>
E-COMMERCE <span>✦</span>
DESIGN <span>✦</span>
DEVELOPMENT <span>✦</span>
BRANDING <span>✦</span>

</div>

</div>


<!-- INTRO -->

<section class="intro">

<div class="container">

<p class="intro-text">
Большинство сайтов пытаются понравиться всем.
<span>Мы делаем наоборот.</span>
Создаём цифровой образ, который подходит именно
вашему бизнесу — и остаётся в памяти.
</p>

</div>

</section>


<!-- WORK -->

<section class="work" id="work">

<div class="container">

<div class="section-top">

<h2 class="section-title">
Работы
</h2>

<div class="section-label">
02 / SELECTED WORK
</div>

</div>


<div class="projects">

<div class="project">

<div class="project-tag">
E-COMMERCE
</div>

<div class="project-content">

<div class="project-number">
01
</div>

<h3>
NORTH<br>
CLOTHING
</h3>

<p>
Интернет-магазин одежды
</p>

</div>

</div>


<div class="project">

<div class="project-tag">
REAL ESTATE
</div>

<div class="project-content">

<div class="project-number">
02
</div>

<h3>
MONO<br>
ESTATE
</h3>

<p>
Сайт премиальной недвижимости
</p>

</div>

</div>


<div class="project">

<div class="project-tag">
RESTAURANT
</div>

<div class="project-content">

<div class="project-number">
03
</div>

<h3>
NOIR<br>
KITCHEN
</h3>

<p>
Сайт ресторана нового формата
</p>

</div>

</div>

</div>

</div>

</section>


<!-- SERVICES -->

<section class="services" id="services">

<div class="container">

<div class="section-top">

<h2 class="section-title">
Что делаем
</h2>

<div class="section-label">
03 / SERVICES
</div>

</div>


<div class="service">

<div class="service-number">01</div>

<h3>Landing</h3>

<p>
Одна страница. Одна задача. Максимум внимания к вашему предложению.
</p>

<div class="arrow">↗</div>

</div>


<div class="service">

<div class="service-number">02</div>

<h3>Business</h3>

<p>
Полноценный сайт компании, который создаёт доверие ещё до первого звонка.
</p>

<div class="arrow">↗</div>

</div>


<div class="service">

<div class="service-number">03</div>

<h3>Shop</h3>

<p>
Интернет-магазин с каталогом, корзиной и удобным оформлением заказа.
</p>

<div class="arrow">↗</div>

</div>


<div class="service">

<div class="service-number">04</div>

<h3>Redesign</h3>

<p>
Берём старый сайт и превращаем его в современный цифровой продукт.
</p>

<div class="arrow">↗</div>

</div>

</div>

</section>


<!-- DIFFERENCE -->

<section class="difference">

<div class="container">

<div class="section-top">

<h2 class="section-title">
Было / Стало
</h2>

<div class="section-label">
04 / DIFFERENCE
</div>

</div>


<div class="compare">

<div class="compare-box bad">

<div class="compare-label">
БЫЛО
</div>

<h3>
«У нас просто есть сайт»
</h3>

<p>
Шаблонный дизайн, много лишнего текста,
непонятная структура и посетитель,
который не знает, куда нажать.
</p>

</div>


<div class="compare-box">

<div class="compare-label">
СТАЛО
</div>

<h3>
«Посмотри, какой сайт»
</h3>

<p>
Чёткое предложение, сильный визуальный образ,
понятный путь клиента и призыв к действию
в нужном месте.
</p>

</div>

</div>

</div>

</section>


<!-- PROCESS -->

<section class="process">

<div class="container">

<div class="section-top">

<h2 class="section-title">
Процесс
</h2>

<div class="section-label">
05 / PROCESS
</div>

</div>


<div class="process-grid">

<div class="step">

<div class="step-number">
01
</div>

<h3>
Разбираемся
</h3>

<p>
Изучаем ваш бизнес, аудиторию,
конкурентов и задачу.
</p>

</div>


<div class="step">

<div class="step-number">
02
</div>

<h3>
Придумываем
</h3>

<p>
Создаём концепцию, структуру
и визуальный язык сайта.
</p>

</div>


<div class="step">

<div class="step-number">
03
</div>

<h3>
Разрабатываем
</h3>

<p>
Превращаем концепцию в
полностью рабочий сайт.
</p>

</div>


<div class="step">

<div class="step-number">
04
</div>

<h3>
Запускаем
</h3>

<p>
Проверяем всё и публикуем
сайт в интернете.
</p>

</div>

</div>

</div>

</section>


<!-- PRICES -->

<section class="pricing" id="prices">

<div class="container">

<div class="section-top">

<h2 class="section-title">
Стоимость
</h2>

<div class="section-label">
06 / PRICING
</div>

</div>


<div class="price-grid">


<div class="price-card">

<h3>START</h3>

<div class="price">
15 000 ₽
</div>

<ul>

<li>Одностраничный сайт</li>
<li>Уникальный дизайн</li>
<li>Адаптация под телефон</li>
<li>Форма заявки</li>
<li>Подключение Telegram</li>

</ul>

<a href="#contact" class="price-button">
Выбрать
</a>

</div>


<div class="price-card featured">

<h3>BUSINESS</h3>

<div class="price">
30 000 ₽
</div>

<ul>

<li>До 7 страниц</li>
<li>Уникальный дизайн</li>
<li>Анимации</li>
<li>Адаптация под устройства</li>
<li>SEO-основа</li>
<li>Аналитика</li>

</ul>

<a href="#contact" class="price-button">
Выбрать
</a>

</div>


<div class="price-card">

<h3>SHOP</h3>

<div class="price">
50 000 ₽
</div>

<ul>

<li>Интернет-магазин</li>
<li>Каталог товаров</li>
<li>Корзина</li>
<li>Форма заказа</li>
<li>Мобильная версия</li>
<li>Индивидуальные функции</li>

</ul>

<a href="#contact" class="price-button">
Выбрать
</a>

</div>

</div>

</div>

</section>


<!-- CTA -->

<section class="cta">

<div class="container">

<h2>
Давайте сделаем<br>
<span>что-то сильное.</span>
</h2>

<p>
Расскажите о своём бизнесе. Мы предложим концепцию
и скажем, какой сайт действительно нужен именно вам.
</p>

<a href="#contact" class="big-button">
Обсудить проект →
</a>

</div>

</section>


<!-- CONTACT -->

<section class="contact" id="contact">

<div class="container">

<div class="contact-grid">

<div class="contact-left">

<div class="section-label">
07 / CONTACT
</div>

<h2>
Есть идея?
<br>
Поговорим.
</h2>

<p>
Заполните форму справа. Никаких сложных брифов —
просто расскажите, что вы хотите получить.
</p>

</div>


<form onsubmit="sendForm(event)">

<input
type="text"
id="name"
placeholder="Ваше имя"
required
>

<input
type="text"
id="contactInput"
placeholder="Telegram / телефон"
required
>

<textarea
id="message"
placeholder="Что нужно сделать?"
required
></textarea>

<button type="submit">
ОТПРАВИТЬ ЗАЯВКУ →
</button>

</form>

</div>

</div>

</section>


<footer>

<div class="container footer">

<div>
NOFRAME © 2026
</div>

<div>
Сайты, которые замечают.
</div>

</div>

</footer>


<script>

/* CUSTOM CURSOR */

const cursor = document.getElementById("cursor");

document.addEventListener("mousemove", function(e) {

    cursor.style.left = e.clientX + "px";
    cursor.style.top = e.clientY + "px";

});


/* TELEGRAM FORM */

function sendForm(event) {

    event.preventDefault();

    const name =
        document.getElementById("name").value;

    const contact =
        document.getElementById("contactInput").value;

    const message =
        document.getElementById("message").value;


    /*
    ==========================================
    ЗАМЕНИ YOUR_USERNAME
    НА СВОЙ TELEGRAM USERNAME
    ==========================================
    */

    const telegramUsername = "YOUR_USERNAME";


    const text =
        "Новая заявка с сайта NOFRAME%0A%0A" +
        "Имя: " + encodeURIComponent(name) +
        "%0AКонтакт: " + encodeURIComponent(contact) +
        "%0AЗадача: " + encodeURIComponent(message);


    window.open(
        "https://t.me/" +
        telegramUsername +
        "?text=" +
        text,
        "_blank"
    );

}

</script>

</body>
</html>