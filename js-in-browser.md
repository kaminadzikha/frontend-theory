# **JavaScript in Browser**

1. **Что такое DOM?**
   DOM (Document Object Model) — это программный интерфейс для веб-документов. Он представляет структуру документа в виде дерева узлов, где каждый узел соответствует части документа, такой как элемент, текст или атрибут. DOM позволяет программам и скриптам динамически изменять содержимое, структуру и стиль веб-страницы.

2. **Типы узлов DOM-дерева?**
   Основные типы узлов DOM-дерева:
    - `Element`: узлы элементов, такие как `<div>`, `<p>`, `<a>`.
    - `Attribute`: узлы атрибутов, связанные с элементами.
    - `Text`: текстовые узлы, содержащие текст внутри элементов.
    - `Comment`: узлы комментариев.
    - `Document`: корневой узел документа.
    - `DocumentFragment`: фрагмент документа, который можно использовать для временного хранения элементов.

3. **Методы поиска элементов в DOM?**
    - `document.getElementById(id)`: находит элемент по идентификатору.
    - `document.getElementsByClassName(className)`: находит элементы по имени класса.
    - `document.getElementsByTagName(tagName)`: находит элементы по имени тега.
    - `document.querySelector(selector)`: находит первый элемент, соответствующий CSS-селектору.
    - `document.querySelectorAll(selector)`: находит все элементы, соответствующие CSS-селектору.

4. **Свойства для перемещения по DOM-дереву?**
    - `parentNode`: родительский узел.
    - `childNodes`: список дочерних узлов.
    - `firstChild`: первый дочерний узел.
    - `lastChild`: последний дочерний узел.
    - `nextSibling`: следующий соседний узел.
    - `previousSibling`: предыдущий соседний узел.

5. **Разница между attribute и property у DOM-элементов?**
    - **Attribute**: относится к HTML-атрибутам, как они указаны в исходном коде. Например, `<input type="text" />` имеет атрибут `type`.
    - **Property**: относится к свойствам объекта в DOM. Например, `element.type` указывает на текущее значение свойства `type`, которое может отличаться от значения атрибута.

6. **Что такое BOM?**
   BOM (Browser Object Model) представляет объекты, предоставляемые браузером, которые позволяют взаимодействовать с браузерным окружением. Например, `window`, `navigator`, `location`, `history` и `screen` — это объекты BOM.

7. **Виды событий в JavaScript?**
    - **Мышь**: `click`, `dblclick`, `mousedown`, `mouseup`, `mousemove`, `mouseover`, `mouseout`, `mouseenter`, `mouseleave`.
    - **Клавиатура**: `keydown`, `keyup`, `keypress`.
    - **Форма**: `submit`, `change`, `focus`, `blur`, `input`.
    - **Документ и окно**: `load`, `unload`, `resize`, `scroll`, `DOMContentLoaded`.
    - **Сетевые события**: `error`, `progress`, `loadend`.

8. **Как добавить обработчик события на DOM-элемент?**
   ```javascript
   element.addEventListener('event', function() {
     // обработчик события
   });
   ```
   Например:
   ```javascript
   document.getElementById('myButton').addEventListener('click', function() {
     alert('Button clicked!');
   });
   ```

9. **Как удалить обработчик события с DOM-элемента?**
   ```javascript
   element.removeEventListener('event', handler);
   ```
   Пример:
   ```javascript
   function handleClick() {
     alert('Button clicked!');
   }

   const button = document.getElementById('myButton');
   button.addEventListener('click', handleClick);
   // Удаление обработчика
   button.removeEventListener('click', handleClick);
   ```

10. **Что такое распространение события (Event Propagation)?**
    Распространение события — это процесс, при котором событие сначала происходит на самом целевом элементе (всплытие события), затем оно перемещается вверх по дереву элементов (сначала к родителю, затем к родителю его родителя и так далее).

11. **Что такое делегирование событий (Event Delegation)?**
    Делегирование событий — это техника, при которой обработчик события назначается на родительский элемент, а не на каждый дочерний элемент. Это позволяет обрабатывать события на дочерних элементах, которые могут быть добавлены динамически.

12. **Как использовать media выражения в JavaScript?**
    Media выражения обычно используются в CSS, но также могут быть использованы в JavaScript через `window.matchMedia()`. Пример:
    ```javascript
    const mediaQuery = window.matchMedia('(max-width: 600px)');
    if (mediaQuery.matches) {
      console.log('Экран меньше 600px');
    } else {
      console.log('Экран больше 600px');
    }
    ```

13. **Расскажите про координаты в браузере?**
    Координаты в браузере можно получить с помощью `getBoundingClientRect()`, который возвращает размер элемента и его позицию относительно видимой области экрана. Пример:
    ```javascript
    const rect = element.getBoundingClientRect();
    console.log(rect.top, rect.left, rect.width, rect.height);
    ```

14. **Разница между HTMLCollection и NodeList?**
    - **HTMLCollection**: коллекция элементов, которые обновляются автоматически при изменении DOM. Обычно возвращается методами типа `getElementsByClassName` или `getElementsByTagName`.
    - **NodeList**: коллекция узлов, не обязательно элементов. Возвращается методами типа `querySelectorAll`. NodeList может быть как живым (обновляющимся), так и статичным (необновляющимся).

15. **Как динамически добавить элемент на HTML-страницу?**
    ```javascript
    const newElement = document.createElement('div');
    newElement.textContent = 'Привет, мир!';
    document.body.appendChild(newElement);
    ```

16. **Разница между feature detection, feature inference и анализом строки user-agent?**
    - **Feature Detection**: проверка поддержки функциональности браузером. Например, проверка наличия метода `fetch`.
    - **Feature Inference**: использование существующих методов или свойств для определения поддержки функции.
    - **Анализ строки user-agent**: использование строки user-agent для определения типа и версии браузера. Этот метод менее надежен, чем feature detection.

17. **Разница между e.preventDefault() и e.stopPropagation()?**
    - **e.preventDefault()**: отменяет действие по умолчанию, связанное с событием (например, отправка формы).
    - **e.stopPropagation()**: останавливает распространение события вверх по дереву DOM (не вызывает обработчики на родительских элементах).

18. **Разница между event.target и event.currentTarget?**
    - **event.target**: элемент, на котором произошло событие.
    - **event.currentTarget**: элемент, на который назначен обработчик события (может отличаться, если используется делегирование событий).

19. **Разница между .stopPropagation() и .stopImmediatePropagation()?**
    - **.stopPropagation()**: останавливает дальнейшее распространение события по дереву DOM.
    - **.stopImmediatePropagation()**: останавливает дальнейшее распространение события и предотвращает выполнение других обработчиков на том же элементе.

20. **Разница между событиями load и DOMContentLoaded?**
    - **load**: срабатывает, когда полностью загружен весь документ, включая все стили, изображения и другие ресурсы.
    - **DOMContentLoaded**: срабатывает, когда весь HTML документ был полностью загружен и разобран, но до загрузки стилей, изображений и других ресурсов.

21. **Сколько аргументов принимает addEventListener?**
    Метод `addEventListener` принимает три аргумента:
    1. Тип события (строка).
    2. Обработчик события (функция).
    3. Опции (необязательный объект или логическое значение, указывающее, должно ли событие быть захваченным или всплывающим).

22. **Разница между innerHTML и outerHTML?**
    - **innerHTML**: возвращает или устанавливает HTML-контент внутри элемента.
    - **outerHTML**: возвращает или устанавливает HTML-контент элемента, включая сам элемент.

23. **Разница между JSON и XML?**
    - **JSON** (JavaScript Object Notation): легковесный формат данных, используемый для обмена данными, легко читается человеком и машиной.
    - **XML** (eXtensible Markup Language): более сложный формат для хранения и передачи данных, использующий разметку для определения структуры.

24. **Как узнать об использовании метода event.preventDefault()?**
    Чтобы определить, вызван ли метод `preventDefault`, можно проверить свойство `defaultPrevented` объекта события:
    ```javascript
    handleEvent(e) {
      if (e.defaultPrevented) {
        console.log('preventDefault был вызван');
      }
    }
    ```

25. **Для чего используется свойство window.navigator?**
    Свойство `window.navigator` предоставляет информацию о браузере и операционной системе пользователя, включая имя браузера, версию, язык и платформу.

26. **Для чего используется метод .focus()?**
    Метод `.focus()` используется для установки фокуса на элементе формы или вводе текста, чтобы пользователь мог начать взаимодействие с ним сразу.

27. **Для чего используется свойство .forms?**
    Свойство `.forms` объекта `document` возвращает коллекцию всех форм в документе.

28. **Для чего используется метод .scrollIntoView()?**
    Метод `.scrollIntoView()` прокручивает элемент так, чтобы он оказался видимым в области просмотра. Это может быть полезно для приведения элемента в фокус.

29. **Разница между методами .submit() и .requestSubmit()?**
    - **.submit()**: отправляет форму, обходя валидацию HTML5 и обработчики события `submit`.
    - **.requestSubmit()**: отправляет форму, включая валидацию HTML5 и вызов обработчиков события `submit`.

30. **Расскажите о IntersectionObserver?**
    `IntersectionObserver` позволяет асинхронно наблюдать за пересечением элемента с областью видимости. Это полезно для реализации ленивой загрузки изображений или триггеров для анимаций.

    Пример:
    ```javascript
    let observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          console.log('Элемент видим!');
        }
      });
    });

    observer.observe(document.querySelector('#myElement'));
    ```

31. **Расскажите о URLSearchParams?**
    `URLSearchParams` предоставляет интерфейс для работы с параметрами строки запроса URL. Он позволяет легко читать, изменять и добавлять параметры.

    Пример:
    ```javascript
    let params = new URLSearchParams('?name=John&age=30');
    console.log(params.get('name')); // John
    console.log(params.has('age'));  // true
    params.append('city', 'New York');
    console.log(params.toString()); // name=John&age=30&city=New+York
    ```

32. **Какие есть ограничения у window.close()?**
    Метод `window.close()` может быть вызван только для окон, которые были открыты с помощью `window.open()`. Попытка закрыть окно, которое не было открыто скриптом, может быть заблокирована браузером.

33. **Как можно создавать пользовательское событие (custom events) в JavaScript?**
    Создание пользовательского события с помощью `CustomEvent`:
    ```javascript
    let event = new CustomEvent('myEvent', { detail: { key: 'value' } });
    element.dispatchEvent(event);
    ```

34. **Что такое IndexedDB? Как работает IndexedDB?**
    IndexedDB — это низкоуровневая база данных, которая позволяет хранить значительные объемы структурированных данных в браузере. Она работает асинхронно и использует ключ-значение для хранения данных. IndexedDB поддерживает транзакции и индексы для улучшения производительности запросов.

35. **Расскажите о методе requestAnimationFrame()?**
    `requestAnimationFrame()` позволяет запланировать выполнение функции перед следующим перерисовыванием экрана. Это эффективный способ для реализации анимаций, так как браузер оптимизирует их выполнение, чтобы избежать лишних перерисовок.

    Пример:
    ```javascript
    function animate() {
      // обновить состояние анимации
      requestAnimationFrame(animate);
    }
    requestAnimationFrame(animate);
    ```