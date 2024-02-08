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
## lesson 4. Контекст и струкуры данных

1. В js массив является "неправильным", потому что в js (динамический язык программирования) - массиву не нужно
задавать длину и не нужно указывать тип данных. Так как массив наследует от object он может иметь функционал хэш-таблиц, 
также методы массива позволяют использовать массив как такие структуры данных как стек и очередь.

2. Привязать контекст:

```
function logger() {
    console.log(`I output only external context: ${this.item}`);
}

const obj = { item: "some value" };

console.log(logger.call(obj))
console.log(logger.apply(obj))
console.log(logger.bind(obj)())
```
3. Бонус. Полифил метода bind():

```
if (!Function.prototype.bind) {
  Function.prototype.bind = function (oThis) {
    if (typeof this !== "function") {
      // ближайший аналог внутренней функции
      // IsCallable в ECMAScript 5
      throw new TypeError(
        "Function.prototype.bind - what is trying to be bound is not callable",
      );
    }

    var aArgs = Array.prototype.slice.call(arguments, 1),
      fToBind = this,
      fNOP = function () {},
      fBound = function () {
        return fToBind.apply(
          this instanceof fNOP && oThis ? this : oThis,
          aArgs.concat(Array.prototype.slice.call(arguments)),
        );
      };

    fNOP.prototype = this.prototype;
    fBound.prototype = new fNOP();

    return fBound;
  };
}
```

## lesson 5. Сложность алгоритмов, ООП

1. Какие бывают алгоритмы сортировок  

- Пузырьковая сортировка и её улучшения

| Сортировка     | худшее   | среднее  | лучшее |
| -----------    |:--------:| :------: | -----: |
| пузырьком      | O($n^2$) | O($n^2$) | O(n)   |
| перемешиванием | O($n^2$) | O($n^2$) | O(n)   |
| расчёской      | O($n^2$) | O($n^2$/2^p) | O(n log n)  |

- Простые сортировки  

| Сортировка     | худшее   | среднее  | лучшее |
| -----------    |:--------:| :------: | -----: |
| вставками      | O($n^2$) | O($n^2$) | O(n)   |
| выбором        | O($n^2$) | O($n^2$) | O($n^2$)  |

- Эффективные сортировки  

| Сортировка     | худшее   | среднее  | лучшее |
| -----------    |:--------:| :------: | -----: |
| быстрая        | O($n^2$) | O(n log n) | O(n)   |
| слиянием       | O(n log n) | O(n log n) | O(n log n)  |
| пирамидельная  | O(n log n) | O(n log n) | O(n log n)  |

2. Устное задание.
3. Создать объект Person несколькими способами, после создать объект Person2, чтобы в нём были доступны методы объекта 
Person. Добавить метод logInfo чтоб он был доступен всем объектам.  

```
// Создание объекта Person (способ 1)
const person1 = {
  name: "Petr",
  sayHello: function () {
    console.log(`Hello, my name is ${this.name}!`);
  },
};

// Создание объекта Person (способ 2: через конструктор)
function Person(name) {
  this.name = name;
}

Person.prototype.sayHello = function () {
  console.log(`Hello, my name is ${this.name}!`);
};

// Создание объекта Person2 с доступом к методам объекта Person
const person2 = new Person("John");

// Добавление метода logInfo
Person.prototype.logInfo = function () {
  console.log(`Logging info ${this.name}`);
};
```

4. Создать класс PersonThree c get и set для поля name и конструктором, сделать класс наследник от класса Person.

```
class Person {
  constructor(name) {
    this._name = name;
  }

  get name() {
    return this._name;
  }

  set name(newName) {
    this._name = newName;
  }
}

class PersonThree extends Person {
  constructor(name) {
    super(name);
  }

}

const person = new Person("John");
console.log(person.name); // Получение значения поля name с использованием геттера
person.name = "Petr"; // Установка нового значения поля name с использованием сеттера
console.log(person.name); // Получение обновленного значения поля name
```

- БОНУС: 
1. Написать функцию, которая вернет массив с первой парой чисел, сумма которых равна total:

```
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
total = 13;

function binarySearch(arr, item, last) {
    let low = 0;
    let high = last - 1;
    
    while (low <= high) {
        let mid = Math.floor((low + high)/2);
        let guess = arr[mid];
        
        if (guess == item) {
            return mid
        };
        
        if (guess > item) {
            high = mid - 1;
        } else {
            low = mid + 1;
        };
    }
    return null
}

const firstSum = (arr, total) => {
    let last = arr[arr.length - 1];
    if(last - total < 0) {
        const first = binarySearch(arr, total - last, last)
        return [arr[first], last]
    } else {
        const first = arr[0];
        last = binarySearch(arr, total - first, last)
        return [first, arr[last]]
    }

}

console.log(firstSum(arr,total))
```

2. Сложность алгоритма из предыдущего задания: O(log n)  

## lesson 6. Ассинхронность в JS

1. 

```
let promiseTwo = new Promise((resolve, reject) => {
   resolve("a");
});

promiseTwo
.then((res) => {
   return res + "b";
})
.then((res) => {
   return res + "с";
})
.finally((res) => {
   return res + "!!!!!!!";
})
.catch((res) => {
   return res + "d";
})
.then((res) => {
   console.log(res);
});

// вывод: "abc"
```

2. 

```
function doSmth() {
   return Promise.resolve("123");
}

doSmth()
.then(function (a) {
   console.log("1", a); //
   return a;
})
.then(function (b) {
   console.log("2", b);
   return Promise.reject("321");
})
.catch(function (err) {
   console.log("3", err);
})
.then(function (c) {
   console.log("4", c);
return c;
});

// вывод: 
// 1 123
// 2 123
// 3 321
// 4 undefined
```

3. 

```
const arr1 = [10, 12, 15, 21];

const arrFilter = (arr) => {
    arr.forEach((item, it)=>{
        setTimeout(() => console.log(arr.indexOf(item)), 3000 * (it+0))
    })
}

arrFilter(arr1);
```

4. Top-level await (глобальный await) - это возможность использовать await на уровень выше, за пределами асинхронной 
функции. Цель такого использования превращение ES-модулей в подобие асинхронных функций. Что позволяет модулям получать 
готовые к использовнанию ресурсы и блокировать модулииЮ импортирующие их. Модули, которые импортируют ожидаемые ресурсы, 
смогут запускать выполнение кода только после получения ресурсов и их предварительной подготовки к использованию. 
Примеры как то такое осуществить:  
- IIFE

```
//a.mjs
import fetch  from "node-fetch";
  export default (async () => {
    const resp = await fetch('https://jsonplaceholder.typicode.com/users');
    users = resp.json();
  })();
  export { users };

//usingAwait.mjs
import promise, {users} from './a.mjs';
  promise.then(() => { 
    console.log('In usingAwait module');
    setTimeout(() => console.log('All users:', users), 100); //user list
  });
```

- Top-level await

```
//a.mjs
const resp = await fetch('https://jsonplaceholder.typicode.com/users');
const users = resp.json();
export { users};

//usingAwait.mjs
import {users} from './a.mjs';

console.log(users);
console.log('In usingAwait module');
```

5. БОНУС ЗАДАНИЕ:  

```
function fetchUrl(url, repeat = 5) {
    fetch(url)
    .then(
      function (value) {
        return value.json();
      },
      function (reason) {
        return repeat > 1
            ? fetchUrl(url, repeat - 1)
            : Promise.reject(reason);
      }
    )
    .then(res => console.log(res))
    .catch(err => console.error(err))
}

fetchUrl(url = 'https://google/com&#39')
```

## lesson 7. Ассинхронность в JS

1.  
KISS — Always Keep It Simple, Stupid (будь проще):  
  - Ваши методы должны быть небольшими (40-50 строк).
  - Каждый метод решает одну проблему.
  - При модификации кода в будущем не должно возникнуть трудностей.
  - Система работает лучше всего, если она не усложняется без надобности.
  - Не устанавливайте целую библиотеку ради одной функции из неё.
  - Не делай того, что не просят.
  - Писать код необходимо надежно и «дубово».  

YAGNI — You are not gonna need it (Вам это не понадобится)
  - Реализуйте только то, что нужно здесь и сейчас, а не в теории, что оно пригодится в будущем.
  - Подчищайте ненужный код (найдите через Git историю при надобности).
  - Программист не должен добавлять новый функционал, о котором его не просят (благими намерениями без должной проверки вы только добавите багов).  

DRY — Don’t Repeat Yourself (Не повторяйся)
  - Избегайте копирования кода.
  - Выносите общую логику.
  - Прежде чем добавлять функционал, проверьте в проекте, может, он уже создан.
  - Константы.

"Антипаттерны" чистого кода:
  - спагетти код - плохо спроектированная, слабо структурированная, запутанная и трудная для понимания программа, особенно содержащая много операторов GOTO (особенно переходов назад), исключений и других конструкций, ухудшающих структурированность. Самый распространённый антипаттерн программирования.
  - Лодочный якорь - это когда программисты оставляют неиспользуемый код в базе, потому что он может понадобиться им позже.
  - Золотой молоток - это когда вы начинаете повсюду применять знаеомый и любимый архитектурный подход. Даже если он неуместен.
  - Боже́ственный объе́кт — антипаттерн объектно-ориентированного программирования, описывающий объект, который хранит в себе «слишком много» или делает «слишком много».

2.  
local storage - объект хранящийся в window, который позволяет долговременно сохранять данные в браузере. Работает в формате ключ-значение.
  - значения хранятся в виде строк;
  - хранение данных неограничено по времени, может быть очищено пользователем вручную или браузером при переполнении автоматически;
  - максимальный объем данных 5mb.  

session storage - объект хранящийся в window, который позволяет сохранять данные в браузере на время сессии. Работает в формате ключ-значение.
  - Сессия страницы создаётся при открытии новой вкладки браузера. Сессия остаётся активной до тех пор, пока открыта вкладка, а состояние сессии сохраняется между перезагрузками. Открытие новой вкладки с таким же адресом приведёт к созданию новой сессии.
  - Значения хранятся в виде строк
  - Максимальный объем данных ограничен размером 5MB  

cookie - это небольшие строки данных, которые хранятся непосредственно в браузере.
  - Мы также можем получить доступ к куки непосредственно из браузера, используя свойство document.cookie.
  - При установке кук можно указывать не только её название и значение, но и другие параметры. Все они являются необязательными и разделяются точкой с запятой:
    - path - определяет путь, по которому будет доступна кука. Он должен быть абсолютным, то есть начинаться с /
    - domain - определяет домен, для которого указана кука. Если не указано, то будет использоваться текущий домен
    - max-age и expires - определяет время жизни куки.max-age указывает, через сколько секунд, а expires указывает точное время, когда кука станет недействительна
    - secure - указывает, что данная кука может быть передана только при запросах по защищённому протоколу HTTPS
    - samesite - определяет, может ли данная кука быть отправлена при кросс-доменном запросе. Значение параметра strict будет предотвращать отправку на другие домены, а lax разрешит отправлять куки с GET-запросами

3. Базовая структура HTML содержит минимум 3 тега: <html>, <head> и <body>. Тег <html> задает язык доккумента. Тег <head> обычно содержит заголовок, ключевые слова, описание страницы и другие служебные данные. Также внутри него подключаются внешние ресурсы, например, стили. Содержимое этого тега не отображается на странице напрямую. А в теге <body> хранится содержание страницы, которое отображается в окне браузера.

```
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Базовая разметка HTML</title>
</head>
<body>
  <h1>Заголовок</h1>
  <p>Какая то информация</p>
</body>
</html>
```

БЭМ(блок, элемент, модификатор) - это список правил для фронтенд-проектов. Основные сущности, которыми оперирует БЭМ, — блок, элемент и модификатор.
  - Блок — это абсолютно независимый компонент страницы. Он отвечает только за отображение элементов — то есть, например, у него не может быть внешних отступов margin. Блоки могут включать в себя другие блоки. Имя блока совпадает с именем селектора по классу:  
  `<div class="popup"></div>`  
  - Элемент — это часть блока, которая имеет смысл только внутри своего блока и отдельно от него не используется. Имя селектора включает имя класса и — через двойное подчёркивание — имя элемента  
  `<h3 class="popup__title">Редактировать профиль</h3>`  
  - Модификатор — это сущность, которая описывает атрибуты блока или элемента: положение, состояние, поведение. Для разделения слов в именах всех сущностей используются дефисы. Модификатор в селекторе именуется через одно подчёркивание после имени элемента или блока.  
  `<div class="popup popup_type_edit-profile"></div>`