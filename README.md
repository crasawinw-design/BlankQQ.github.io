<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Тест: Устав МООО «РСО» и Положения (2026)</title>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body {
            font-family: 'Segoe UI', Roboto, Arial, sans-serif;
            background: linear-gradient(145deg, #0b1a2e 0%, #1c3a5c 100%);
            min-height: 100vh; display: flex; align-items: center; justify-content: center; padding: 20px;
        }
        .test-wrapper {
            max-width: 900px; width: 100%; background: rgba(255, 255, 255, 0.96);
            border-radius: 32px; box-shadow: 0 25px 50px -8px rgba(0, 0, 0, 0.6), inset 0 1px 4px rgba(255, 255, 255, 0.5);
            padding: 35px 40px; backdrop-filter: blur(4px); border: 1px solid rgba(255, 255, 255, 0.6);
        }
        h1 { font-size: 28px; font-weight: 700; color: #0a1e30; margin-bottom: 6px; display: flex; align-items: center; gap: 12px; flex-wrap: wrap; }
        h1 span { background: #0033a0; color: white; padding: 6px 14px; border-radius: 60px; font-size: 16px; font-weight: 600; text-transform: uppercase; }
        .subhead { color: #2c4b6c; font-size: 15px; border-left: 5px solid #ffb400; padding: 12px 18px; margin-bottom: 25px; font-weight: 500; background: #eef5ff; border-radius: 12px; line-height: 1.5; }
        .progress-bar { background: #dde6f0; height: 8px; border-radius: 40px; margin: 15px 0 12px; overflow: hidden; }
        .progress-fill { background: linear-gradient(90deg, #0033a0, #3b7fd4); width: 0%; height: 100%; border-radius: 40px; transition: width 0.25s ease; }
        .counter { display: flex; justify-content: space-between; font-size: 14px; color: #26527c; font-weight: 600; margin-bottom: 22px; }
        .question-text { font-size: 22px; font-weight: 600; line-height: 1.4; color: #0b1e30; background: #f6fbff; padding: 22px 26px; border-radius: 20px; margin: 12px 0 28px; border: 1px solid #bdd1e8; box-shadow: 0 6px 12px -6px rgba(0, 30, 60, 0.12); word-break: break-word; }
        .options { display: flex; flex-direction: column; gap: 12px; margin-bottom: 28px; }
        .option { display: flex; align-items: flex-start; gap: 14px; background: white; padding: 16px 22px; border-radius: 18px; border: 2px solid #d0dfef; cursor: pointer; transition: all 0.15s ease; font-size: 16px; line-height: 1.45; color: #143450; font-weight: 500; box-shadow: 0 2px 4px rgba(0, 0, 0, 0.02); }
        .option:hover { background: #f0f8ff; border-color: #5a8ec9; }
        .option.selected { background: #e3f0ff; border-color: #0033a0; box-shadow: 0 4px 12px rgba(0, 60, 140, 0.15); }
        .option input[type="radio"] { appearance: none; width: 22px; height: 22px; border: 2px solid #6d8fb8; border-radius: 50%; margin-top: 2px; flex-shrink: 0; background: white; position: relative; }
        .option input[type="radio"]:checked { border-color: #0033a0; background: #0033a0; box-shadow: inset 0 0 0 5px white, 0 0 0 1px #0033a0; }
        .option label { flex: 1; cursor: pointer; }
        .actions { display: flex; gap: 15px; justify-content: flex-end; flex-wrap: wrap; }
        .btn { padding: 14px 36px; border-radius: 60px; font-weight: 700; font-size: 16px; border: none; cursor: pointer; transition: all 0.15s; display: inline-flex; align-items: center; justify-content: center; gap: 8px; letter-spacing: 0.2px; background: white; color: #1b3f66; border: 2px solid #b7cde2; box-shadow: 0 4px 8px rgba(0, 0, 0, 0.02); }
        .btn-primary { background: #0033a0; color: white; border: 2px solid #0033a0; box-shadow: 0 8px 18px -6px #0033a0; }
        .btn-primary:hover { background: #00227a; border-color: #00227a; transform: scale(1.02); }
        .btn-primary:disabled { background: #9aabc0; border-color: #9aabc0; box-shadow: none; transform: none; cursor: not-allowed; opacity: 0.7; }
        .btn-outline { background: transparent; border: 2px solid #49749e; color: #1e3f60; }
        .btn-outline:hover { background: #e8f0fa; border-color: #0033a0; }
        .result-screen { text-align: left; padding: 10px 0; }
        .result-screen h2 { font-size: 32px; font-weight: 800; color: #0033a0; margin-bottom: 8px; display: flex; align-items: center; gap: 12px; }
        .stat-badge { background: #e3f0ff; border-radius: 60px; padding: 16px 28px; font-size: 20px; font-weight: 700; display: inline-block; margin: 12px 0 24px; color: #0b2d4b; border: 1px solid #b7cde2; }
        .stat-badge span { color: #0033a0; font-size: 28px; margin-right: 4px; }
        .answers-review { max-height: 420px; overflow-y: auto; border: 1px solid #d0dfef; border-radius: 20px; padding: 16px 20px; background: #fafdff; margin: 20px 0 25px; }
        .review-item { border-bottom: 1px solid #d9e6f2; padding: 16px 0; }
        .review-item:last-child { border-bottom: none; }
        .review-question { font-weight: 700; color: #0f2a42; margin-bottom: 8px; font-size: 16px; }
        .review-answer { font-size: 15px; line-height: 1.5; margin-bottom: 4px; display: flex; gap: 8px; align-items: baseline; }
        .review-correct { color: #1e7a3c; font-weight: 600; }
        .review-wrong { color: #b13e3e; font-weight: 600; }
        .review-badge { font-size: 13px; font-weight: 700; padding: 2px 10px; border-radius: 40px; background: #d9e6f2; color: #224466; display: inline-block; }
        .review-correct .review-badge { background: #cde8d9; color: #0a5e2e; }
        .review-wrong .review-badge { background: #fadada; color: #a32f2f; }
        .hidden { display: none !important; }
        .hint { font-size: 14px; color: #507397; margin-top: 16px; text-align: center; font-weight: 500; border-top: 1px dashed #b7cde2; padding-top: 18px; }
        @media (max-width: 650px) {
            .test-wrapper { padding: 22px 20px; }
            .question-text { font-size: 19px; padding: 18px; }
            .option { font-size: 15px; padding: 14px 16px; }
            .btn { padding: 12px 24px; font-size: 15px; width: 100%; }
            .actions { flex-direction: column; }
            h1 { font-size: 22px; }
            .result-screen h2 { font-size: 26px; }
        }
    </style>
</head>
<body>

<div class="test-wrapper" id="app">
    <div id="quizScreen">
        <h1>📋 Тест РСО (2026) <span>Устав и положения</span></h1>
        <div class="subhead">Проверка знаний: руководство, даты, устав, символика, форма, СанПиН, права, обязанности, награды</div>
        <div class="progress-bar"><div class="progress-fill" id="progressFill"></div></div>
        <div class="counter"><span id="questionCounter">Вопрос 1 из 65</span><span id="scoreCounter">Правильно: 0</span></div>
        <div class="question-text" id="questionText">Загрузка...</div>
        <div class="options" id="optionsContainer"></div>
        <div class="actions">
            <button class="btn btn-primary" id="confirmBtn" disabled>Подтвердить</button>
            <button class="btn btn-outline hidden" id="nextBtn">Следующий вопрос →</button>
        </div>
        <div class="hint" id="hintMessage"></div>
    </div>
    <div id="resultScreen" class="result-screen hidden">
        <h2>🏁 Тест завершён!</h2>
        <div class="stat-badge" id="finalScore"></div>
        <div class="actions" style="justify-content: flex-start; margin-bottom: 15px;">
            <button class="btn btn-outline" id="reviewBtn">📖 Посмотреть правильные ответы</button>
            <button class="btn btn-primary" id="restartBtn">🔄 Пройти заново</button>
        </div>
        <div id="reviewContainer" class="answers-review hidden"></div>
    </div>
</div>

<script>
    (function() {
        // -------------------------------------------------------------
        // БАЗА ВОПРОСОВ (65 вопросов, данные 2025–2026)
        // -------------------------------------------------------------
        const rawQuestions = [
            // 1. Членство в РСО
            {
                question: "Согласно Уставу МООО «РСО», какое минимальное требование к возрасту для вступления в организацию?",
                options: ["14 лет", "16 лет", "18 лет", "Не имеет значения"],
                correct: 0
            },
            // 2. Цель деятельности
            {
                question: "Какова цель деятельности МООО «РСО» согласно Уставу?",
                options: [
                    "Проведение спортивных соревнований среди студентов",
                    "Организация временной занятости обучающихся в свободное от учёбы время",
                    "Исключительно культурно-массовые мероприятия",
                    "Политическая деятельность"
                ],
                correct: 1
            },
            // 3. Высший орган
            {
                question: "Какой орган является высшим руководящим органом организации?",
                options: ["Наблюдательный совет", "Правление", "Съезд", "Центральный штаб (ЦШ)"],
                correct: 2
            },
            // 4. Съезд — периодичность
            {
                question: "Как часто созывается Съезд?",
                options: ["1 раз в 2 года", "1 раз в 5 лет", "Каждый год", "1 раз в 3 года"],
                correct: 3
            },
            // 5. Внеочередной съезд
            {
                question: "Кто может потребовать созыва внеочередного Съезда?",
                options: [
                    "Более половины региональных отделений",
                    "Один региональный руководитель",
                    "Только Председатель Правления",
                    "Командир ЦШ единолично"
                ],
                correct: 0
            },
            // 6. Наблюдательный совет — заседания
            {
                question: "Как часто должны проводиться заседания Наблюдательного совета?",
                options: ["Не реже одного раза в год", "Не реже двух раз в год", "Не реже одного раза в 3 года", "Без ограничений"],
                correct: 1
            },
            // 7. Наблюдательный совет — состав
            {
                question: "Кто входит в состав Наблюдательного совета?",
                options: [
                    "Только представители региональных отделений",
                    "Только Командир ЦШ и Комиссар",
                    "Председатель Наблюдательного совета, его заместители, Председатель Правления, представители Окружных штабов и иные члены",
                    "Все бойцы РСО"
                ],
                correct: 2
            },
            // 8. Председатель Наблюдательного совета — стаж
            {
                question: "Какое требование предъявляется к Председателю Наблюдательного совета и его Первому заместителю?",
                options: ["Состоять в Организации более 3 лет", "Быть студентом очной формы", "Возраст не старше 35 лет", "Состоять в Организации более 10 лет"],
                correct: 3
            },
            // 9. Правление — членство
            {
                question: "Кто может быть членом Правления?",
                options: ["Любые члены РСО", "Полностью дееспособные люди, состоящие в Организации более 3 лет", "Только Председатели региональных отделений", "Только выпускники"],
                correct: 1
            },
            // 10. Правление — сроки
            {
                question: "Сколько сроков подряд может занимать должность Председателя Правления одно и то же лицо?",
                options: ["Не более двух сроков", "Не более одного срока", "Не ограничено", "Не более трёх сроков"],
                correct: 0
            },
            // 11. ЦШ — заседания
            {
                question: "Как часто должны созываться заседания ЦШ?",
                options: ["Не реже одного раза в 3 месяца", "Не реже одного раза в 6 месяцев", "Раз в год", "Раз в 2 года"],
                correct: 1
            },
            // 12. Исполнительный орган
            {
                question: "Кто является единоличным исполнительным органом организации?",
                options: ["Председатель Наблюдательного совета", "Командир ЦШ", "Председатель Правления", "Комиссар ЦШ"],
                correct: 1
            },
            // 13. Окружной штаб — срок
            {
                question: "Срок полномочий Командира Окружного штаба?",
                options: ["1 год", "3 года", "5 лет", "2 года"],
                correct: 1
            },
            // 14. ЦКРК — расшифровка
            {
                question: "Что такое ЦКРК?",
                options: ["Центральная контрольно-ревизионная комиссия", "Центральный комитет по кадрам", "Центральный культурный отдел", "Центральный комитет развития"],
                correct: 0
            },
            // 15. ЦКРК — срок
            {
                question: "На какой срок избираются ЦКРК и КРК региональных отделений?",
                options: ["2 года", "1 год", "3 года", "5 лет"],
                correct: 2
            },
            // 16. Символика — книга
            {
                question: "Что символизирует открытая книга на старом логотипе РСО?",
                options: ["Трудолюбие", "Рассвет", "Знание", "Единство"],
                correct: 2
            },
            // 17. Символика — мастерок
            {
                question: "Что символизирует мастерок на старом логотипе РСО?",
                options: ["Труд / трудолюбие", "Строительство", "Знание", "Восходящее солнце"],
                correct: 0
            },
            // 18. Новый логотип — слоган
            {
                question: "Какой слоган используется на современном логотипе организации?",
                options: ["«РСО — это мы»", "«Труд крут»", "«Вперёд, студенты!»", "«Студенческие отряды — сила»"],
                correct: 1
            },
            // 19. ЛСО — определение
            {
                question: "Что такое линейный студенческий отряд (ЛСО)?",
                options: [
                    "Спортивная команда вуза",
                    "Только строительный отряд",
                    "Коллектив обучающихся для временной занятости и реализации общественно полезной программы",
                    "Кружок по интересам"
                ],
                correct: 2
            },
            // 20. ЛСО — численность
            {
                question: "Какая минимальная численность линейного студенческого отряда?",
                options: ["Не менее 5 человек", "Не менее 10 человек", "Не менее 15 человек", "Не менее 20 человек"],
                correct: 1
            },
            // 21. Приём в отряд
            {
                question: "Как происходит приём в члены отряда?",
                options: [
                    "Общим собранием отряда или в индивидуальном порядке при наличии членства в МООО «РСО»",
                    "Только по приказу командира ЦШ",
                    "Автоматически при зачислении в вуз",
                    "Только по решению Правления"
                ],
                correct: 0
            },
            // 22. Права бойца
            {
                question: "Какое из перечисленных прав есть у бойца?",
                options: [
                    "Не соблюдать «сухой закон»",
                    "Избирать и быть избранным в руководящие органы отряда",
                    "Пропускать собрания без причины",
                    "Не участвовать в мероприятиях"
                ],
                correct: 1
            },
            // 23. «Сухой закон»
            {
                question: "Что означает требование «сухого закона» в период трудового семестра?",
                options: ["Запрет на курение", "Полный запрет на алкоголь", "Запрет на выезд", "Обязательное ношение формы"],
                correct: 1
            },
            // 24. Обязанности — учебная программа
            {
                question: "Что обязан выполнять боец согласно Положению?",
                options: [
                    "Только производственные задания",
                    "Только общественные поручения",
                    "Только спортивные нормативы",
                    "Учебную программу подготовки бойца и программу по месту учёбы"
                ],
                correct: 3
            },
            // 25. Награды — Благодарность
            {
                question: "Кому может быть объявлена Благодарность РСО?",
                options: [
                    "Только ветеранам",
                    "Действующим членам, отработавшим не менее 1 года, и иным лицам за заслуги",
                    "Только командирам",
                    "Только первокурсникам"
                ],
                correct: 1
            },
            // 26. Награды — Почётная грамота
            {
                question: "Сколько лет нужно отработать для представления к Почётной грамоте РСО?",
                options: ["Не менее 1 года", "Не менее 3 лет", "Не менее 2 лет", "Не менее 4 лет"],
                correct: 2
            },
            // 27. Награды — высшая степень
            {
                question: "Какая награда является высшей степенью награды в МООО «РСО»?",
                options: ["Почётный знак «За активную работу в студенческих отрядах»", "Благодарность РСО", "Почётная грамота РСО", "Значок «Отличник РСО»"],
                correct: 0
            },
            // 28. Награды — квота Благодарность
            {
                question: "Какова квота на представление к Благодарности РСО?",
                options: ["1 на 50 членов", "1 на 200 членов", "1 на 100 членов регионального отделения", "Не ограничена"],
                correct: 2
            },
            // 29. Награды — квота Почётный знак
            {
                question: "Какова квота на представление к Почётному знаку РСО в обычный год?",
                options: ["1 на 500 членов", "1 на 100 членов", "1 на 200 членов", "1 на 1000 членов"],
                correct: 0
            },
            // 30. Делегаты Съезда
            {
                question: "Кто является делегатами Съезда?",
                options: [
                    "Только командиры региональных отделений",
                    "Все бойцы РСО",
                    "Председатель Наблюдательного совета, Председатель Правления, члены Наблюдательного совета, Правления, ЦШ и ЦКРК",
                    "Только представители вузов"
                ],
                correct: 2
            },
            // 31. Руководство — Командир ЦШ (2026)
            {
                question: "Кто является руководителем (командиром) Центрального штаба РСО по данным на 2026 год?",
                options: ["Михаил Киселев", "Ярослав Зубащенко", "Юлия Дрожжина", "Роман Уколов"],
                correct: 1
            },
            // 32. Руководство — Председатель Правления (2026)
            {
                question: "Кто является Председателем Правления РСО по данным на 2026 год?",
                options: ["Юлия Дрожжина", "Михаил Киселев", "Ярослав Зубащенко", "Роман Уколов"],
                correct: 0
            },
            // 33. Руководство — Председатель Наблюдательного совета (2026)
            {
                question: "Кто является Председателем Наблюдательного совета РСО по данным на 2026 год?",
                options: ["Юлия Дрожжина", "Ярослав Зубащенко", "Михаил Киселев", "Роман Уколов"],
                correct: 2
            },
            // 34. Руководство — Председатель ЦКРК (2025)
            {
                question: "Кто был переизбран Председателем Центральной контрольно-ревизионной комиссии (ЦКРК) на VII Съезде в 2025 году?",
                options: ["Роман Уколов", "Михаил Киселев", "Ярослав Зубащенко", "Юлия Дрожжина"],
                correct: 0
            },
            // 35. Бойцовка — определение
            {
                question: "Что такое «бойцовка»?",
                options: ["Спортивная куртка", "Куртка защитного цвета — форменная одежда бойца", "Значок отряда", "Флаг отряда"],
                correct: 1
            },
            // 36. Бойцовка — когда обязательна
            {
                question: "В каких случаях ношение бойцовки обязательно?",
                options: [
                    "Только на Съезде",
                    "Только в первый день целины",
                    "На мероприятиях МООО «РСО» всех уровней и в течение трудового семестра",
                    "По желанию"
                ],
                correct: 2
            },
            // 37. Бойцовка — запрет
            {
                question: "Что строго запрещено в форменной одежде (бойцовке)?",
                options: [
                    "Носить поверх другой одежды",
                    "Стирать",
                    "Надевать на учёбу",
                    "Употреблять алкоголь, наркотики, курить, быть в состоянии опьянения"
                ],
                correct: 3
            },
            // 38. Бойцовка — шеврон на левом рукаве
            {
                question: "Какой шеврон располагается на левом рукаве на расстоянии 60–80 мм от плечевого шва?",
                options: ["Шеврон вуза", "Шеврон МООО «РСО»", "Шеврон отряда", "Шеврон местного штаба"],
                correct: 1
            },
            // 39. Бойцовка — нашивка члена РСО
            {
                question: "Где располагается нашивка члена МООО «РСО»?",
                options: ["Над правым карманом", "На спине", "Над левым нагрудным карманом (либо на нём)", "На воротнике"],
                correct: 2
            },
            // 40. Бойцовка — целинные кирпичи (значки)
            {
                question: "Где располагаются целинные кирпичи (значки за трудовой семестр)?",
                options: [
                    "На левой стороне воротника, снизу вверх по годам",
                    "На правой стороне воротника",
                    "На левом рукаве",
                    "На спине"
                ],
                correct: 0
            },
            // 41. СанПиН — площадь спален
            {
                question: "Какова минимальная площадь на одного человека в спальном помещении (СанПиН)?",
                options: ["Не менее 2 м²", "Не менее 6 м²", "Не менее 3 м²", "Не менее 4 м²"],
                correct: 3
            },
            // 42. СанПиН — расстояние от дороги
            {
                question: "На каком расстоянии от проезжей дороги рекомендуется располагать лагерь?",
                options: ["Не менее 100–200 м", "Не менее 50 м", "Не менее 300 м", "Не менее 500 м"],
                correct: 0
            },
            // 43. СанПиН — запрет в палатках
            {
                question: "Что запрещается устраивать в брезентовых палатках?",
                options: ["Кровати", "Вешалки", "Тумбочки", "Печи и электричество в палатках менее чем на 25 человек"],
                correct: 3
            },
            // 44. СанПиН — медпункт (площадь кабинета врача)
            {
                question: "Какова минимальная площадь кабинета врача-педиатра в медпункте (СанПиН)?",
                options: ["Не менее 3 м²", "Не менее 10 м²", "Не менее 5–7 м²", "Не менее 15 м²"],
                correct: 1
            },
            // 45. СанПиН — изолятор
            {
                question: "На сколько коек (палат) рассчитывается изолятор в лагере?",
                options: ["На 1 койку", "На 5 коек", "На 2–3 койки (не менее двух палат)", "На 10 коек"],
                correct: 2
            },
            // 46. СанПиН — противопожарный щит
            {
                question: "На какое количество человек должен быть противопожарный щит в жилой зоне?",
                options: ["На 20 человек", "На 100 человек", "На 10 человек", "На 40 человек"],
                correct: 3
            },
            // 47. СанПиН — сушка одежды
            {
                question: "Какая площадь предусмотрена для чистки, сушки и хранения рабочей одежды?",
                options: ["0,2 м² на 1 человека", "0,5 м² на 1 человека", "1 м² на 1 человека", "Не регламентируется"],
                correct: 0
            },
            // 48. Устав — требования к члену
            {
                question: "Кто, согласно Уставу, может быть членом МООО «РСО»?",
                options: [
                    "Только граждане РФ с 18 лет",
                    "Гражданин РФ, иностранный гражданин или лицо без гражданства, достигший 14 лет, студент очной формы, признающий Устав",
                    "Только бюджетники",
                    "Только с опытом работы"
                ],
                correct: 1
            },
            // 49. Правление — заседания
            {
                question: "Как часто должны проводиться заседания Правления?",
                options: ["Не реже одного раза в год", "Не реже двух раз в год", "Не реже одного раза в 3 года", "Раз в месяц"],
                correct: 1
            },
            // 50. Наблюдательный совет — кворум
            {
                question: "При каком условии заседание Наблюдательного совета имеет право принимать решения?",
                options: ["Если присутствует более половины его членов", "Если присутствуют все", "Если присутствует Председатель", "Если присутствует треть"],
                correct: 0
            },
            // 51. Дата VII Съезда
            {
                question: "Когда состоялся VII очередной Съезд РСО, на котором был избран новый руководящий состав?",
                options: ["14 марта 2025 года", "15 марта 2025 года", "14 марта 2026 года", "15 марта 2026 года"],
                correct: 0
            },
            // 52. Дата утверждения Устава в новой редакции
            {
                question: "Какой датой утверждён Устав МООО «РСО» в новой редакции?",
                options: ["14 марта 2025 года", "15 марта 2025 года", "1 января 2025 года", "14 марта 2026 года"],
                correct: 0
            },
            // 53. Руководство — Комиссар ЦШ (2025)
            {
                question: "Кто был избран на должность заместителя руководителя (комиссара) Центрального штаба РСО на VII Съезде?",
                options: ["Юлия Позднякова", "Мария Корнилова", "Юлия Дрожжина", "Роман Уколов"],
                correct: 0
            },
            // 54. Нашивка Правления — расположение
            {
                question: "Где нашивается нашивка Правления РСО, если член Правления также занимает должность в региональном штабе?",
                options: [
                    "Над правым карманом куртки",
                    "Над левым карманом",
                    "На левом рукаве",
                    "На спине"
                ],
                correct: 0
            },
            // 55. Значки участников мероприятий
            {
                question: "Где располагаются значки участников мероприятий МООО «РСО»?",
                options: [
                    "На левой стороне воротника",
                    "На правой стороне воротника или правом кармане",
                    "На левом кармане",
                    "На спине"
                ],
                correct: 1
            },
            // 56. Наградные знаки — расположение
            {
                question: "Где располагаются наградные знаки МООО «РСО» и региональных штабов?",
                options: ["На левом кармане куртки", "На правом кармане", "На левом рукаве", "На воротнике"],
                correct: 0
            },
            // 57. СанПиН — продолжительность смены в палаточном лагере
            {
                question: "Какова рекомендуемая продолжительность смены в палаточном лагере (СанПиН 2.4.4.3048-13)?",
                options: ["Не более 14 дней", "Не более 21 дня", "Не более 30 дней", "Не более 7 дней"],
                correct: 1
            },
            // 58. СанПиН — расстояние от контейнеров до жилых зданий
            {
                question: "Каково минимальное расстояние от контейнеров для отходов до жилых зданий и мест отдыха?",
                options: ["Не менее 10 м", "Не менее 25 м", "Не менее 50 м", "Не менее 5 м"],
                correct: 1
            },
            // 59. СанПиН — медпункт (процедурный кабинет)
            {
                question: "Какова минимальная площадь процедурного кабинета в медпункте лагеря?",
                options: ["Не менее 10 м²", "Не менее 12 м²", "Не менее 15 м²", "Не менее 8 м²"],
                correct: 1
            },
            // 60. СанПиН — изолятор (площадь на место)
            {
                question: "Какова площадь изолятора из расчёта на одно место?",
                options: ["6 м²", "4 м²", "8 м²", "10 м²"],
                correct: 0
            },
            // 61. Экс-нашивки — расположение
            {
                question: "Где располагаются экс-нашивки (бывших командиров, комиссаров и т.д.)?",
                options: ["Под левым нагрудным карманом", "Над правым карманом", "На левом рукаве", "На спине"],
                correct: 0
            },
            // 62. СанПиН — проживание мальчиков и девочек
            {
                question: "Требование к спальным комнатам для мальчиков и девочек:",
                options: ["Могут быть общими", "Должны быть отдельными", "Только для детей старше 14 лет", "Не регламентируется"],
                correct: 1
            },
            // 63. Награды — юбилейный год (квота)
            {
                question: "Что происходит с квотой на Почётный знак РСО в юбилейный год?",
                options: ["Остаётся прежней", "Увеличивается в 2 раза", "Уменьшается", "Не присуждается"],
                correct: 1
            },
            // 64. СанПиН — вместимость спальни (новое строительство)
            {
                question: "Какова максимальная вместимость спальни во вновь строящихся зданиях лагерей (СанПиН)?",
                options: ["Не более 10 мест", "Не более 5 мест", "Не более 8 мест", "Не более 15 мест"],
                correct: 1
            },
            // 65. СанПиН — гигиеническая подготовка работников
            {
                question: "С какой периодичностью работники лагеря проходят профессиональную гигиеническую подготовку и аттестацию?",
                options: ["Один раз при приёме на работу", "Не реже 1 раза в год", "Не реже 1 раза в 2 года", "Не реже 1 раза в 5 лет"],
                correct: 1
            }
        ];

        // -------------------------------------------------------------
        // ПЕРЕМЕШИВАНИЕ
        // -------------------------------------------------------------
        function shuffleArray(arr) {
            for (let i = arr.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [arr[i], arr[j]] = [arr[j], arr[i]];
            }
            return arr;
        }

        // Перемешивает варианты внутри вопроса и возвращает новый объект
        function shuffleOptions(questionObj) {
            const correctText = questionObj.options[questionObj.correct];
            const shuffledOptions = shuffleArray([...questionObj.options]);
            const newCorrectIndex = shuffledOptions.indexOf(correctText);
            return {
                question: questionObj.question,
                options: shuffledOptions,
                correct: newCorrectIndex
            };
        }

        // Готовит полностью перемешанный набор вопросов
        function prepareQuestions() {
            // 1. Перемешиваем порядок вопросов
            const shuffledQuestions = shuffleArray([...rawQuestions]);
            // 2. Для каждого вопроса перемешиваем варианты
            return shuffledQuestions.map(q => shuffleOptions(q));
        }

        // -------------------------------------------------------------
        // СОСТОЯНИЕ
        // -------------------------------------------------------------
        let questions = prepareQuestions(); // массив текущих вопросов
        let currentIndex = 0;
        let userAnswers = new Array(questions.length).fill(null);
        let score = 0;
        let answered = false;

        const quizScreen = document.getElementById('quizScreen');
        const resultScreen = document.getElementById('resultScreen');
        const questionText = document.getElementById('questionText');
        const optionsContainer = document.getElementById('optionsContainer');
        const confirmBtn = document.getElementById('confirmBtn');
        const nextBtn = document.getElementById('nextBtn');
        const progressFill = document.getElementById('progressFill');
        const questionCounter = document.getElementById('questionCounter');
        const scoreCounter = document.getElementById('scoreCounter');
        const hintMessage = document.getElementById('hintMessage');
        const finalScore = document.getElementById('finalScore');
        const reviewContainer = document.getElementById('reviewContainer');
        const reviewBtn = document.getElementById('reviewBtn');
        const restartBtn = document.getElementById('restartBtn');

        // -------------------------------------------------------------
        // ОТРИСОВКА
        // -------------------------------------------------------------
        function renderQuestion() {
            const q = questions[currentIndex];
            questionText.textContent = q.question;
            optionsContainer.innerHTML = '';

            q.options.forEach((opt, idx) => {
                const optionDiv = document.createElement('div');
                optionDiv.className = 'option';
                if (userAnswers[currentIndex] === idx) optionDiv.classList.add('selected');

                const radio = document.createElement('input');
                radio.type = 'radio';
                radio.name = 'question';
                radio.value = idx;
                radio.id = `opt_${idx}`;
                radio.checked = (userAnswers[currentIndex] === idx);
                radio.disabled = answered;

                const label = document.createElement('label');
                label.htmlFor = `opt_${idx}`;
                label.textContent = opt;

                optionDiv.addEventListener('click', () => {
                    if (answered) return;
                    document.querySelectorAll('.option').forEach(el => el.classList.remove('selected'));
                    optionDiv.classList.add('selected');
                    radio.checked = true;
                    userAnswers[currentIndex] = idx;
                    confirmBtn.disabled = false;
                });

                optionDiv.appendChild(radio);
                optionDiv.appendChild(label);
                optionsContainer.appendChild(optionDiv);
            });

            if (answered) {
                confirmBtn.classList.add('hidden');
                nextBtn.classList.remove('hidden');
                document.querySelectorAll('input[name="question"]').forEach(r => r.disabled = true);
                hintMessage.textContent = `✅ Правильный ответ: ${q.options[q.correct]}`;
            } else {
                confirmBtn.classList.remove('hidden');
                nextBtn.classList.add('hidden');
                hintMessage.textContent = '';
                confirmBtn.disabled = (userAnswers[currentIndex] === null);
            }

            const total = questions.length;
            progressFill.style.width = `${((currentIndex + 1) / total) * 100}%`;
            questionCounter.textContent = `Вопрос ${currentIndex + 1} из ${total}`;
            scoreCounter.textContent = `Правильно: ${score}`;
        }

        // -------------------------------------------------------------
        // ПОДТВЕРЖДЕНИЕ
        // -------------------------------------------------------------
        function confirmAnswer() {
            if (answered) return;
            if (userAnswers[currentIndex] === null) return;

            answered = true;
            const q = questions[currentIndex];
            const selected = userAnswers[currentIndex];

            if (selected === q.correct) score++;

            document.querySelectorAll('input[name="question"]').forEach(r => r.disabled = true);
            confirmBtn.classList.add('hidden');
            nextBtn.classList.remove('hidden');
            hintMessage.textContent = `✅ Правильный ответ: ${q.options[q.correct]}`;
            scoreCounter.textContent = `Правильно: ${score}`;
        }

        // -------------------------------------------------------------
        // СЛЕДУЮЩИЙ
        // -------------------------------------------------------------
        function nextQuestion() {
            if (!answered) return;
            if (currentIndex < questions.length - 1) {
                currentIndex++;
                answered = false;
                renderQuestion();
            } else {
                showResults();
            }
        }

        // -------------------------------------------------------------
        // РЕЗУЛЬТАТЫ
        // -------------------------------------------------------------
        function showResults() {
            quizScreen.classList.add('hidden');
            resultScreen.classList.remove('hidden');

            const total = questions.length;
            const percent = Math.round((score / total) * 100);
            finalScore.innerHTML = `<span>${score}</span> из ${total} правильных (${percent}%)`;

            reviewContainer.classList.add('hidden');
            reviewBtn.textContent = '📖 Посмотреть правильные ответы';
            reviewBtn.dataset.open = 'false';
        }

        // -------------------------------------------------------------
        // ПРОСМОТР ОТВЕТОВ
        // -------------------------------------------------------------
        function toggleReview() {
            const isOpen = reviewBtn.dataset.open === 'true';
            if (isOpen) {
                reviewContainer.classList.add('hidden');
                reviewBtn.textContent = '📖 Посмотреть правильные ответы';
                reviewBtn.dataset.open = 'false';
                return;
            }

            reviewContainer.innerHTML = '';
            questions.forEach((q, idx) => {
                const userAns = userAnswers[idx];
                const isCorrect = userAns === q.correct;
                const item = document.createElement('div');
                item.className = 'review-item';

                const questionDiv = document.createElement('div');
                questionDiv.className = 'review-question';
                questionDiv.textContent = `${idx + 1}. ${q.question}`;

                const userAnswerDiv = document.createElement('div');
                userAnswerDiv.className = 'review-answer ' + (isCorrect ? 'review-correct' : 'review-wrong');
                const userAnswerText = userAns !== null ? q.options[userAns] : '— (нет ответа)';
                userAnswerDiv.innerHTML = `<span class="review-badge">${isCorrect ? '✓ Верно' : '✗ Неверно'}</span> Ваш ответ: ${userAnswerText}`;

                const correctAnswerDiv = document.createElement('div');
                correctAnswerDiv.className = 'review-answer review-correct';
                correctAnswerDiv.innerHTML = `<span class="review-badge">✓ Правильно</span> ${q.options[q.correct]}`;

                item.appendChild(questionDiv);
                item.appendChild(userAnswerDiv);
                if (!isCorrect) item.appendChild(correctAnswerDiv);

                reviewContainer.appendChild(item);
            });

            reviewContainer.classList.remove('hidden');
            reviewBtn.textContent = '🙈 Скрыть правильные ответы';
            reviewBtn.dataset.open = 'true';
        }

        // -------------------------------------------------------------
        // ПЕРЕЗАПУСК (с новым перемешиванием вопросов и вариантов)
        // -------------------------------------------------------------
        function restartTest() {
            // Заново готовим полностью перемешанный набор вопросов
            questions = prepareQuestions();
            currentIndex = 0;
            userAnswers = new Array(questions.length).fill(null);
            score = 0;
            answered = false;

            quizScreen.classList.remove('hidden');
            resultScreen.classList.add('hidden');
            reviewContainer.classList.add('hidden');
            reviewBtn.dataset.open = 'false';

            hintMessage.textContent = '';
            confirmBtn.classList.remove('hidden');
            nextBtn.classList.add('hidden');
            confirmBtn.disabled = true;

            renderQuestion();
        }

        // -------------------------------------------------------------
        // СОБЫТИЯ
        // -------------------------------------------------------------
        confirmBtn.addEventListener('click', confirmAnswer);
        nextBtn.addEventListener('click', nextQuestion);
        reviewBtn.addEventListener('click', toggleReview);
        restartBtn.addEventListener('click', restartTest);

        renderQuestion();
    })();
</script>
</body>
</html>
