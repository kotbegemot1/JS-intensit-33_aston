# Интенсив по JS от aston



## lesson 1. Основы git

Домашнее задание к первому уроку:

![Первый скриншот](https://github.com/kotbegemot1/JS-intensit-33_aston/blob/main/images/1big.png)
![Первый скриншот](https://github.com/kotbegemot1/JS-intensit-33_aston/blob/main/images/2big.png)

 
## lesson 2. Сети, JS

1. Метод OPTIONS - это тип HTTP запроса, который используется для запроса информации о доступных действиях для взаимодействия с целевым ресурсом.
    - Безопасный - Да
    - Идемпотентный - Да
    - Кушируемый - Нет  
  Чаще всего является пре-запросом, которыый вызывается перед запросом который может изменять данные на сервере.  
  Позволяет запросить информацию о сервере, в том числе информацию о допускаемых к использованию на сервере HTTP-методов.  
  В ответе от сервера пиходит заголовок Allow со списком поддерживаемых методов. Также в заголовке ответа может включаться информация о поддерживаемых расширениях.  

2.  Ключевая осбенность протокола HTTP/3 в том, что он определяет использование протокола QUIC (Quick UDP Internet Connections) в качестве транспорта для HTTP/2. QUIC представляет собой надстройку над протоколом UDP, поддерживающую мультиплексирование нескольких соединений и обеспечивающую методы шифрования, эквивалентные TLS/SSL.
  Особенности по средствам QUIC:
  - Возможность мгновенно установить соединение;
  - Высокая скорость(берёт от UDP высокую скорость передачи) но и высокая безопасность, аналогичная TLS (по сути QUIC предоставляет возможность использования TLS поверх UDP);
  - Контроль за целостностью потока, предотвращающий потерю пакетов;

3. AbortController — это класс, представленный в JavaScript, который позволяет управлять асинхронными операциями, такими как Fetch запросы, Promise, fs, setTimeout и setInterval. С его помощью можно прерывать выполнение асинхронных задач и предотвращать нежелательные побочные эффекты от выполнения задач, которые уже неактуальны. AbortController предоставляет надежный и стандартизированный механизм для управления асинхронными задачами. Он позволяет разработчикам контролировать выполнение асинхронных операций, предотвращать выполнение ненужных запросов и избегать утечек памяти.
Он имеет единственный метод abort() и единственное свойство signal.

4. string:  
    `let single = 'single-quoted';  
    let double = "double-quoted";  
    let backticks = `backticks`;`  
  
  number:  
    `let num = 2;
    let num2 = Number(3);`  
  
  boolen:  
    `let bool = true;  
    let bool2 = Boolen(1);  
    let bool3 = 3 > 4;`  
  
  null:  
    `let personObj = null;  
    let element = document.querySelector('несуществующий класс');`  
  
  undefined:  
    `let name;
    let und = (function asd(){})();`  
  
  symbol:
    `const sym = Symbol('dd');`  
  
  bigint:  
    `const biggy = 9997000254740991n;  
    const alsoBig = BigInt(9997000254999999);`  

5. const и let ограничены областью видимости блока и если мы попытаемся обратиться к этим переменным до их объявления, то получим ReferenceError.
Объект ReferenceError представляет ошибку, возникающую при обращении к переменной, которая не существует (или не была инициализирована) в текущей области видимости.