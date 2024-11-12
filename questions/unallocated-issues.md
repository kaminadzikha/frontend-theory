Темы и вопросы:

Веб-разработка: Архитектура, запросы, CORS

1. Архитектура проекта и ее отличие от структуры. Какие архитектуры использовал?
5. Что такое микрофронтенды?
7. Зачем нужен ESLint, настройка и плагины.

ООП и паттерны

1. Что такое ООП?
2. Какие паттерны знаешь? (порождающие, структурные, поведенческие)
1. Как работают классы под капотом? Прототипы.

CSS и верстка

3. Flexbox.
4. Позиционирование: absolute, fixed, sticky.
5. Препроцессоры CSS (SCSS, SASS).
6. Отличие display: block, inline-block, inline.!!!

Git

1. Что такое Git Flow, GitHub Flow?
2. Как минимизировать количество merge-конфликтов?
3. Отличие merge и rebase.
4. Зачем нужны git hooks (pre-commit и др.)?
5. Что такое code review и зачем оно нужно?

какие методы жизн цикла не воспроизводятся в функциональных компонентах

Вопросы Руслану с собесов:

1. Сначала спрашивает о последних проектах, составе команды, что интересного делал.
2. Где лучше организовать работу с аксесс токеном с точки зрения React/Redux? Как бы я реализовал логику на получение
   новой пары токенов в кастомном мидлвейре?
3. Поток выполнения в Redux (Про то, что сначала есть action, потом его обрабатывает middleware, потом в reducer и т.д)?
4. Как у тебя была реализована регистрация/авторизация на последнем проекте?
5. Как определить есть ли свойство у объекта? И в чем их различия?
6. Как получить все значения объекта?
7. Промисы?
8. Event loop?
9. Был ли опыт работы с RxJS?
10. По вебпаку спросил про code splitting(чанки), про встряхивание дерева и про проксирование(как можно настроить через
    вебпак)?
11. Вопросы по хукам React, какие использовал?
12. call, apply, bind?
13. Что такое прототип?
14. Что такое чистая функция?
15. Был ли опыт с RTK Query и общее мнение, если работал с ним?
16. Отличие 401 от 403 статуса?
17. Что такое Дженерик?
18. Разница постфикса и префикса инкремента и декремента?
19. Что такое Порталы в React?
18. Задача найди наибольшее нечетное в массиве вот таких строк:
    const data = ["101", "2", "311", "400", "502", "43"];
    (нужно решить через reduce).

1. Расскажи про HTTP
2. CORS
3. Какие типы позиционирования знаешь?
4. Как центрировать блок по середине страницы, а также, что такое флексы и как это можно с ними реализовать.
5. Специфичность стилей
6. Что такое каскадность в CSS?
7. Разница между блочным и строчным элементом.
8. Что такое композиция? И как это реализовать?
9. Что такое карирование? Также рассказать про реализацию.
10. Язык JS является однопоточным? Что такое синхронные и асинхронные задачи? Event Loop
11. requestAnimationFrame.
12. Заблокируют ли промисы перерисовку страницы?
13. Задача:
    setTimeout(() => console.log('timeout'));

Promise.resolve(1)
.then((x) => x + 1)
.then(x => {throw x})
.catch(x => console.log(x))
.then((x) => console.log(x))
.catch(x => console.log(x))

14. Задача: написать реализацию TODO, на реакте с типизацией на TS.
15. Задача: написать свой debounce.
16. Задача: написать свой метод bind.