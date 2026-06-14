<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <title>Энергос - Производство электроэнергии</title>
    <link href="https://fonts.googleapis.com/css2?family=Oswald:wght@400;500;700&display=swap" rel="stylesheet">
    
    <style>
        html {
            scroll-behavior: smooth;
        }

        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            color: #333333;
            background-color: #1a0505;
            overflow: hidden;
        }

        #top-anchor {
            position: absolute;
            top: 0;
            left: 0;
        }

        #header-wrapper {
            background-color: #ffffff;
            border-bottom: 3px solid #800020;
            padding: 0 40px;
            height: 70px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            box-sizing: border-box;
        }

        #site-name {
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
            letter-spacing: 3px;
            font-size: 28px;
            color: #800020;
            margin: 0;
        }

        #nav {
            list-style-type: none;
            padding: 0;
            margin: 0;
            display: flex;
        }

        #nav li {
            margin-left: 20px;
        }

        #nav a {
            color: #333333;
            text-decoration: none;
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 14px;
            padding-bottom: 5px;
            border-bottom: 2px solid transparent;
            transition: color 0.3s, border-bottom 0.3s;
        }

        #nav a:hover {
            color: #800020;
            border-bottom: 2px solid #800020;
        }

        #horizontal-wrapper {
            display: flex;
            height: calc(100vh - 70px);
            margin-top: 70px;
            overflow-x: auto;
            overflow-y: hidden;
            scroll-behavior: smooth;
        }

        #horizontal-wrapper::-webkit-scrollbar {
            display: none;
        }
        #horizontal-wrapper {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }

        #slide-home, #slide-goal, #slide-info, #slide-input, #slide-equip, #slide-ops, #slide-output, #slide-control {
            width: 100vw;
            height: 100%;
            flex-shrink: 0;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            background-color: #f4f7f6;
        }

        #hero, #banner-goal, #banner-info, #banner-input, #banner-equip, #banner-ops, #banner-output, #banner-control {
            min-height: calc(100vh - 70px);
            width: 100%;
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #1a0505;
            flex-shrink: 0;
        }

        #hero img, #banner-goal img, #banner-info img, #banner-input img, #banner-equip img, #banner-ops img, #banner-output img, #banner-control img {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            opacity: 0.3;
            z-index: 1;
        }

        #hero h1, #banner-goal h2, #banner-info h2, #banner-input h2, #banner-equip h2, #banner-ops h2, #banner-output h2, #banner-control h2 {
            position: relative;
            z-index: 2;
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
            letter-spacing: 6px;
            font-size: 56px;
            color: #ffffff;
            text-shadow: 3px 3px 0px #4a0011;
            border-bottom: 6px solid #ffcccc;
            padding-bottom: 20px;
            text-align: center;
            margin: 0;
        }

        #scroll-hint {
            position: absolute;
            bottom: 40px;
            z-index: 2;
            color: #ffcccc;
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 18px;
        }

        section {
            flex-shrink: 0;
            width: 1000px;
            margin: 40px auto;
            padding: 50px 40px;
            background-color: #ffffff;
            border-top: 4px solid #800020;
            box-shadow: 0 4px 20px rgba(0,0,0,0.08);
            box-sizing: border-box;
        }

        section h3 {
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: #800020;
            font-size: 24px;
            border-bottom: 2px solid #f0f0f0;
            padding-bottom: 15px;
            margin-top: 0;
        }

        p {
            font-size: 16px;
            line-height: 1.7;
            color: #555555;
        }

        #img-row {
            display: flex;
            gap: 20px;
            margin-top: 30px;
        }

        #img-row img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            border: 3px solid #800020;
            padding: 4px;
            background-color: #ffffff;
            box-shadow: 0 4px 10px rgba(128, 0, 32, 0.15);
            box-sizing: border-box;
            transition: transform 0.3s, border-color 0.3s;
        }

        #img-row img:hover {
            transform: scale(1.05);
            border-color: #ffcccc;
        }

        #footer {
            background-color: #e0e0e0;
            padding: 30px 40px;
            margin-top: auto;
            border-top: 3px solid #cccccc;
            width: 100%;
            box-sizing: border-box;
        }

        #footer p {
            color: #444444;
            margin: 5px 0;
            font-size: 14px;
        }

        #footer-title {
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
            font-size: 18px;
            color: #800020;
            margin-bottom: 15px;
            border-bottom: 1px solid #999999;
            padding-bottom: 5px;
        }

        #go-top-btn {
            position: fixed;
            bottom: 40px;
            right: 40px;
            background-color: #800020;
            color: #ffffff;
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 16px;
            padding: 15px 25px;
            text-decoration: none;
            border: 3px solid #ffcccc;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
            z-index: 1000;
            transition: background-color 0.3s;
        }

        #go-top-btn:hover {
            background-color: #4a0011;
            border-color: #ffffff;
        }


        #company-stats {
            list-style-type: none;
            padding: 0;
            margin: 20px 0 0 0;
            display: flex;
            justify-content: space-between;
        }
        #company-stats li {
            text-align: center;
            border: 2px solid #800020;
            padding: 20px;
            width: 30%;
            background-color: #fdfdfd;
            transition: transform 0.3s, background-color 0.3s;
        }
        #company-stats li:hover {
            transform: scale(1.05);
            background-color: #fff0f0;
        }
        #company-stats li strong {
            display: block;
            font-family: 'Oswald', sans-serif;
            font-size: 32px;
            color: #800020;
            margin-bottom: 5px;
        }
        #company-stats li span {
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 14px;
            color: #333333;
        }

        details {
            background-color: #f9f9f9;
            border: 2px solid #800020;
            padding: 15px;
            margin-top: 20px;
            transition: background-color 0.3s;
        }
        details[open] {
            background-color: #fff0f0;
        }
        summary {
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 18px;
            color: #800020;
            cursor: pointer;
            list-style: none;
        }
        summary::-webkit-details-marker {
            display: none;
        }

        #chart-container {
            display: flex;
            align-items: center;
            gap: 40px;
            margin-top: 30px;
            padding: 20px;
            border: 2px solid #f0f0f0;
            background-color: #fafafa;
        }
        #energy-chart {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            background: conic-gradient(#800020 0% 60%, #4a0011 60% 85%, #ffcccc 85% 100%);
            position: relative;
            transition: transform 0.4s;
            flex-shrink: 0;
        }
        #energy-chart:hover {
            transform: scale(1.1);
        }
        #chart-inner {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 60%;
            height: 60%;
            background-color: #fafafa;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Oswald', sans-serif;
            font-size: 24px;
            color: #800020;
        }
        #chart-legend {
            list-style-type: none;
            padding: 0;
            margin: 0;
        }
        #chart-legend li {
            margin-bottom: 15px;
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
            letter-spacing: 1px;
            display: flex;
            align-items: center;
            font-size: 16px;
        }
        #legend-color-1, #legend-color-2, #legend-color-3 {
            display: inline-block;
            width: 20px;
            height: 20px;
            margin-right: 15px;
        }
        #legend-color-1 { background-color: #800020; }
        #legend-color-2 { background-color: #4a0011; }
        #legend-color-3 { background-color: #ffcccc; }

        #flip-row {
            display: flex;
            gap: 20px;
            margin-top: 30px;
            perspective: 1000px; /* Для 3D эффекта */
        }
        #flip-card-1, #flip-card-2, #flip-card-3 {
            width: 33.33%;
            height: 220px;
            text-align: center;
        }
        #flip-inner-1, #flip-inner-2, #flip-inner-3 {
            position: relative;
            width: 100%;
            height: 100%;
            transition: transform 0.8s;
            transform-style: preserve-3d;
        }
        #flip-card-1:hover #flip-inner-1, #flip-card-2:hover #flip-inner-2, #flip-card-3:hover #flip-inner-3 {
            transform: rotateY(180deg);
        }
        #flip-front-1, #flip-front-2, #flip-front-3, #flip-back-1, #flip-back-2, #flip-back-3 {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            border: 3px solid #800020;
            box-sizing: border-box;
            padding: 20px;
        }
        #flip-front-1, #flip-front-2, #flip-front-3 {
            background-color: #ffffff;
        }
        #flip-back-1, #flip-back-2, #flip-back-3 {
            background-color: #800020;
            color: #ffffff;
            transform: rotateY(180deg);
        }

        #equip-details {
            border: none;
            padding: 0;
            background-color: transparent;
        }
        #equip-details summary {
            background-color: #800020;
            color: #ffffff;
            padding: 15px;
            margin-bottom: 5px;
            border-left: 5px solid #4a0011;
        }
        #equip-details summary:hover {
            background-color: #4a0011;
        }
        #equip-details p {
            background-color: #f9f9f9;
            padding: 15px;
            border-left: 5px solid #ffcccc;
            margin-top: 0;
        }

        #steps-list {
            list-style-type: none;
            padding: 0;
            counter-reset: step-counter;
        }
        #steps-list li {
            counter-increment: step-counter;
            padding: 15px;
            margin-bottom: 10px;
            border-left: 5px solid #cccccc;
            background-color: #ffffff;
            transition: border-color 0.3s, background-color 0.3s, transform 0.3s;
            cursor: default;
        }
        #steps-list li::before {
            content: counter(step-counter) ". ";
            font-family: 'Oswald', sans-serif;
            font-size: 20px;
            color: #800020;
            margin-right: 10px;
        }
        #steps-list li:hover {
            border-left-color: #800020;
            background-color: #fff0f0;
            transform: translateX(10px);
        }

        #tabs-container {
            margin-top: 20px;
        }
        input[name="output-tabs"] {
            display: none; /* Скрываем радио-кнопки */
        }
        #tab-label-1, #tab-label-2, #tab-label-3 {
            display: inline-block;
            padding: 12px 25px;
            background-color: #e0e0e0;
            color: #333333;
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
            letter-spacing: 1px;
            cursor: pointer;
            border: 2px solid #800020;
            border-bottom: none;
            margin-right: 5px;
            transition: background-color 0.3s, color 0.3s;
        }
        #tab-label-1:hover, #tab-label-2:hover, #tab-label-3:hover {
            background-color: #fff0f0;
        }
        #tab-content-1, #tab-content-2, #tab-content-3 {
            display: none;
            padding: 25px;
            border: 2px solid #800020;
            background-color: #ffffff;
            border-top: 4px solid #800020;
        }
        #tab-radio-1:checked ~ #tab-label-1, #tab-radio-2:checked ~ #tab-label-2, #tab-radio-3:checked ~ #tab-label-3 {
            background-color: #800020;
            color: #ffffff;
        }
        #tab-radio-1:checked ~ #tab-content-1, #tab-radio-2:checked ~ #tab-content-2, #tab-radio-3:checked ~ #tab-content-3 {
            display: block;
        }

        #alarm-btn {
            display: inline-block;
            padding: 15px 30px;
            background-color: #4a0011;
            color: #ffffff;
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 18px;
            cursor: pointer;
            border: 3px solid #1a0505;
            margin-top: 20px;
        }
        #alarm-btn:hover {
            background-color: #ff0000;
            animation: alarm-pulse 0.5s infinite;
        }
        @keyframes alarm-pulse {
            0% { background-color: #ff0000; color: #ffffff; }
            50% { background-color: #ffffff; color: #ff0000; border-color: #ff0000; }
            100% { background-color: #ff0000; color: #ffffff; }
        }

    </style>
</head>
<body>

    <div id="top-anchor"></div>

    <div id="header-wrapper">
        <h3 id="site-name">Энергос</h3>
        <ul id="nav">
            <li><a href="#slide-home">Главная</a></li>
            <li><a href="#slide-goal">Цель</a></li>
            <li><a href="#slide-info">Общая информация</a></li>
            <li><a href="#slide-input">Входные компоненты</a></li>
            <li><a href="#slide-equip">Оборудование</a></li>
            <li><a href="#slide-ops">Технологические операции</a></li>
            <li><a href="#slide-output">Выход процесса</a></li>
            <li><a href="#slide-control">Управление и контроль</a></li>
        </ul>
    </div>

    <div id="horizontal-wrapper">

        <div id="slide-home">
            <div id="hero">
                <img src="fon.jpg" alt="Главная">
                <h1>АО «Энергос»</h1>
                <div id="scroll-hint">Пролистайте вправо →</div>
            </div>
            <section id="home-company-info">
                <h3>О компании</h3>
                <p>АО «Энергос» — один из крупнейших производителей электрической и тепловой энергии в регионе. Мы создаем фундамент для развития экономики.</p>
                <ul id="company-stats">
                    <li><strong>15</strong><span>Электростанций</span></li>
                    <li><strong>10 000</strong><span>МВт Мощности</span></li>
                    <li><strong>5.2 Млн</strong><span>Потребителей</span></li>
                </ul>
                <div id="img-row">
                    <img src="of2.jpg" alt="Офис">
                    <img src="tec.jpg" alt="Тэц">
                    <img src="boy.jpg" alt="Инженер">
                </div>
            </section>
        </div>

        <div id="slide-goal">
            <div id="banner-goal">
                <img src="images/goal_background.jpg" alt="Цель баннер">
                <h2>Цель проекта</h2>
            </div>
            <section>
                <h3>Цель проекта</h3>
                <p>Изучить технологический процесс производства электроэнергии на тепловых электростанциях.</p>
                <details>
                    <summary>▶ Раскрыть задачи проекта</summary>
                    <p>1. Проанализировать входные компоненты.<br>2. Изучить принцип работы оборудования.<br>3. Описать параметры выхода продукции.<br>4. Рассмотреть системы контроля.</p>
                </details>
            </section>
        </div>

        <div id="slide-info">
            <div id="banner-info">
                <img src="inj.jpg" alt="Информация баннер">
                <h2>Общая информация</h2>
            </div>
            <section>
                <h3>Энергетика сегодня</h3>
                <p>Производство электроэнергии — это сложный процесс преобразования различных видов энергии. Структура выработки АО «Энергос» опирается на традиционные и возобновляемые источники.</p>
                
                <div id="chart-container">
                    <div id="energy-chart">
                        <div id="chart-inner">Вещества</div>
                    </div>
                    <ul id="chart-legend">
                        <li><div id="legend-color-1"></div>Газ (60%)</li>
                        <li><div id="legend-color-2"></div>Уголь (25%)</li>
                        <li><div id="legend-color-3"></div>Гидро (15%)</li>
                    </ul>
                </div>

                <div id="img-row">
                    <img src="tec.jpg" alt="Электростанция">
                    <img src="ep.jpg" alt="Линии ЭП">
                    <img src="st.jpg" alt="Генератор">
                </div>
            </section>
        </div>

        <div id="slide-input">
            <div id="banner-input">
                <img src="gas2.jpg" alt="Компоненты баннер">
                <h2>Входные компоненты</h2>
            </div>
            <section>
                <h3>Ресурсы для генерации</h3>
                <p>Для работы ТЭС требуются топливо, вода и воздух. Наведите курсор на карточку, чтобы узнать подробности.</p>
                
                <!-- 3D Переворачивающиеся карточки -->
                <div id="flip-row">
                    <div id="flip-card-1">
                        <div id="flip-inner-1">
                            <div id="flip-front-1">
                                <h4>Органическое топливо</h4>
                                <p>(Наведите курсор)</p>
                            </div>
                            <div id="flip-back-1">
                                <p>Природный газ и уголь. Сгорают в топке, выделяя тепловую энергию.</p>
                            </div>
                        </div>
                    </div>
                    <div id="flip-card-2">
                        <div id="flip-inner-2">
                            <div id="flip-front-2">
                                <h4>Питательная вода</h4>
                                <p>(Наведите курсор)</p>
                            </div>
                            <div id="flip-back-2">
                                <p>Проходит глубокую очистку. Нагревается до пара, который вращает турбину.</p>
                            </div>
                        </div>
                    </div>
                    <div id="flip-card-3">
                        <div id="flip-inner-3">
                            <div id="flip-front-3">
                                <h4>Атмосферный воздух</h4>
                                <p>(Наведите курсор)</p>
                            </div>
                            <div id="flip-back-3">
                                <p>Необходим для процесса горения. Подается дутьевыми вентиляторами.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
        </div>

        <div id="slide-equip">
            <div id="banner-equip">
                <img src="01.jpg" alt="Оборудование баннер">
                <h2>Оборудование</h2>
            </div>
            <section>
                <h3>Основные машины</h3>
                
                <details id="equip-details">
                    <summary>Паровой котел</summary>
                    <p>Устройство для получения пара высокого давления за счет сжигания топлива. Температура пара достигает 560°C.</p>
                </details>
                
                <details id="equip-details">
                    <summary>Паровая турбина</summary>
                    <p>Преобразует кинетическую энергию пара в механическую энергию вращения ротора.</p>
                </details>

                <details id="equip-details">
                    <summary>Турбогенератор</summary>
                    <p>Преобразует механическую энергию вала турбины в электрическую энергию переменного тока.</p>
                </details>
            </section>
        </div>

        <div id="slide-ops">
            <div id="banner-ops">
                <img src="images/ops_background.jpg" alt="Операции баннер">
                <h2>Технологические операции</h2>
            </div>
            <section>
                <h3>Этапы процесса</h3>
                
                <ol id="steps-list">
                    <li>Подача топлива и воздуха в топку котла, процесс горения.</li>
                    <li>Нагрев питательной воды, превращение ее в пар.</li>
                    <li>Подача пара в турбину, вращение ротора.</li>
                    <li>Выработка электроэнергии в генераторе.</li>
                    <li>Охлаждение пара и возврат воды в котел.</li>
                </ol>
            </section>
        </div>

        <div id="slide-output">
            <div id="banner-output">
                <img src="par.jpg" alt="Выход баннер">
                <h2>Выход процесса</h2>
            </div>
            <section>
                <h3>Результаты производства</h3>
                
                <div id="tabs-container">
                    <input type="radio" name="output-tabs" id="tab-radio-1" checked>
                    <input type="radio" name="output-tabs" id="tab-radio-2">
                    <input type="radio" name="output-tabs" id="tab-radio-3">
                    
                    <label for="tab-radio-1" id="tab-label-1">Электроэнергия</label>
                    <label for="tab-radio-2" id="tab-label-2">Тепловая энергия</label>
                    <label for="tab-radio-3" id="tab-label-3">Экология</label>
                    
                    <div id="tab-content-1">
                        <p>Основной продукт. Вырабатывается на напряжении 10-20 кВ, затем повышается на подстанциях для передачи по ЛЭП. Частота в сети — 50 Гц.</p>
                    </div>
                    <div id="tab-content-2">
                        <p>Побочный продукт ТЭЦ. Отработавший пар используется для нагрева сетевой воды, которая поступает в системы отопления городов.</p>
                    </div>
                    <div id="tab-content-3">
                        <p>Дымовые газы проходят многоступенчатую очистку: золоуловители, десульфуризация, фильтры мелкодисперсной фракции.</p>
                    </div>
                </div>
            </section>
        </div>

        <div id="slide-control">
            <div id="banner-control">
                <img src="rab.jpg" alt="Управление баннер">
                <h2>Управление и контроль</h2>
            </div>
            <section>
                <h3>АСУ ТП и безопасность</h3>
                <p>Управление станцией осуществляется с помощью автоматизированных систем.</p>
                
                <div id="alarm-btn">⚠ Тест аварийной сигнализации</div>

                <div id="img-row">
                    <img src="dat.jpg" alt="Управление 1">
                    <img src="2.jpg" alt="Управление 2">
                    <img src="3.jpg" alt="Управление 3">
                </div>
            </section>
            
            <div id="footer">
                <div id="footer-title">Данные автора</div>
                <p>Имя Фамилия: Арина Набаева</p>
                <p>Email: arinanabaeva07@icloud.com</p>
            </div>
        </div>

    </div>

    <a href="#slide-home" id="go-top-btn">В начало ↑</a>

</body>
</html>
