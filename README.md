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

## lesson 6. Фссинхронность в JS

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