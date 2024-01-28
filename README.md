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

4. Cоздания примитивных значений: 
  
  - string:  
```let single = 'single-quoted';```  
```let double = "double-quoted";```  
```let backticks = `backticks`;```
  
  - string:

    ```let num = 2;```  
    ```let num2 = `Number(3)`;```
  
  - boolen:  
    ```let bool = true;```  
    ```let bool2 = Boolen(1);```  
    ```let bool3 = 3 > 4;```  
  
  - null:  
    ```let personObj = null;```  
    ```let element = document.querySelector('несуществующий класс');```  
  
  - undefined:  
    ```let name;```  
    ```let und = (function asd(){})();```  
  
  - symbol:  
    ```const sym = Symbol('dd');```  
  
  - bigint:  
    ```const biggy = 9997000254740991n;```  
    ```const alsoBig = BigInt(9997000254999999);```  

5. const и let ограничены областью видимости блока и если мы попытаемся обратиться к этим переменным до их объявления, то получим ReferenceError.
Объект ReferenceError представляет ошибку, возникающую при обращении к переменной, которая не существует (или не была инициализирована) в текущей области видимости.

6. Примеры:  

```
const res = "B" + "a" + (1 - "hello");
console.log(res); // "BaNaN"
```

```
const res2 = (true && 3) + "d";
console.log(res2); // "3d"
```

```
const res3 = Boolean(true && 3) + "d";
console.log(res3); // "trued"
```

## lesson 3. Объекты и ффункции

1. Способы создания объектов:  
- 1 способ:  

`const counter = { count: 0 }`

- 2 cпособ:  

```
function Counter(count=0) {
    this.count = count
    return this
}
const counter = Counter()
```
- 3 способ:  

`const counter3 = Object.assign({}, {count: 0})`

2. Способы копирования объектов:  
- 1 способ(structuredClone):  

```const someArr = { 'a': 1, 'b':2 };
const deepArr = structuredClone(someArr);
```

- 2 cпособ(lodash):  

```
import cloneDeep from 'lodash.clonedeep';
const someArr = { 'a': 1, 'b':2 };
const deepArr = cloneDeep(someArr)
```

- 3 способ(JSON.parse, JSON.stringify):  

```
const someArr = { 'a': 1, 'b':2 };
const deep = JSON.parse(JSON.stringify(itemsInCart));
```
3. Создать функцию makeCounter:  
- 1 способ(function declaration):

```
function makeCounter() {
    let counter = 0;
    function increaseCounter() {
        counter += 1;
        console.log(counter);
    }
    return increaseCounter
}

const increaseCounter = makeCounter();
```

- 2 способ(function expression):

```
const makeCounter = function(count) {
  let counter = 0;
  counter += count;
  return counter
}
```

- 3 способ(named function expression):

```
const makeCounter = function counter(count) {
  let counter = 0;
  counter += count;
  return counter
}
```

- 4 способ(arrow function):

```
const makeCounter = (count) => {
  let counter = 0;
  counter += count;
  return counter
}
```

- 5 способ(anonymous function):

```
const makeCounter = function(count) {
  let counter = 0;
  counter += count;
  return counter
}
```

4. *Функция глубокого сравнения:

```
const obj1 = { 
  here: { 
    is: "on", 
    other: "3" 
    },
  object: "Y"
  };

const obj2 = { 
  here: { 
    is: "on", 
    other: "2" 
    }, 
  object: "Y" 
  };

const deepEqual = (object1, object2) => {

  const objKeys1 = Object.keys(object1);
  const objKeys2 = Object.keys(object2);

  if (objKeys1.length !== objKeys2.length) return false;

  for (let key of objKeys1) {
    const value1 = object1[key];
    const value2 = object2[key];

    const isObjects = isObject(value1) && isObject(value2);

    if ((isObjects && !deepEqual(value1, value2)) ||
      (!isObjects && value1 !== value2)
    ) {
      return false;
    }
  }
  return true;
};

const isObject = (object) => {
  return object != null && typeof object === "object";
};

console.log(deepEqual(obj1, obj2)) //false
```

5. *Функция переворачивающая строку:  

```
function reverseStr(str) {
    return str.split('').reverse().join('');
}
```
