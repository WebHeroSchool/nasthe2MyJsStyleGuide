# :herb: My JS Style Guide :seedling:

### 1. Присваивание значений
Если переменной планируется присваивать новые значения, используй `let` вместо `var`:
``` js
// плохо
var count = 1;
if (true) {
  count += 1;
}

// хорошо
let count = 1;
if (true) {
  count += 1;
}
```

### 2. Создание объектов
При создании объектов используй JS синтаксис. Не ссылайся на глобальный объект.
``` js
// плохо
const item = new Object();

// хорошо
const item = {};
```

### 3. Доступ к параметрам объекта
Для доступа к параметрам объекта используй точечную запись (dot notation):
``` js
const luke = {
  jedi: true,
  age: 28,
};

// плохо
const isJedi = luke['jedi'];

// хорошо
const isJedi = luke.jedi;
```

### 4. Использование переменных в качестве ключа-значения объекта
Если перед описанием объекта объявлена и определена некая переменная, которая должна использоваться в качестве пары ключ-значение,
используй сокращенную запись для внесения этой переменной в параметры объекта
``` js
const lukeSkywalker = 'Luke Skywalker';

// плохо
const obj = {
  lukeSkywalker: lukeSkywalker,
};

// хорошо
const obj = {
  lukeSkywalker,
};
```

### 5. Группировка сокращенных записей параметров объектов
При использовании вышеобозначенной сокращенной записи параметров группируй их в самом начале списка параметров объекта. 
Это упрощает работу с ними.
``` js
const anakinSkywalker = 'Anakin Skywalker';
const lukeSkywalker = 'Luke Skywalker';

// плохо
const obj = {
  episodeOne: 1,
  twoJediWalkIntoACantina: 2,
  lukeSkywalker,
  episodeThree: 3,
  mayTheFourth: 4,
  anakinSkywalker,
};

// хорошо
const obj = {
  lukeSkywalker,
  anakinSkywalker,
  episodeOne: 1,
  twoJediWalkIntoACantina: 2,
  episodeThree: 3,
  mayTheFourth: 4,
};
```


### 6. Добавление значений в массив
При добавлении значений в массив используй метод `Array.prototype.push()` вместо присваивания напрямую:
``` js
const someStack = [];

// плохо
someStack[someStack.length] = 'abracadabra';

// хорошо
someStack.push('abracadabra');
```

### 7. Копирование массивов
Для копирования массивов используй синтаксис `spread`:
``` js
// плохо
const len = items.length;
const itemsCopy = [];
let i;

for (i = 0; i < len; i += 1) {
  itemsCopy[i] = items[i];
}

// хорошо
const itemsCopy = [...items];
```

### 8. Стрелочные функции
Когда необходимо использовать анонимную функцию (как при передаче callback), используйте стрелочные функции. 
Это создаст версию функции, которая выполняется в требуемом контексте, и выглядит лаконичнее.
``` js
// плохо
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});

// хорошо
[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});
```

### 9. Возведение в степень
Для возведения в степень предпочтительнее использовать оператор `**`, а не метод `Math.pow()`:
``` js
// плохо
const binary = Math.pow(2, 10);

// хорошо
const binary = 2 ** 10;
```

### 10. Сравнение
При использовании условных операторов используй сокращенную запись для бинарного типа, а явную запись для строк и чисел:
``` js
// плохо
if (isValid === true) {
  // ...
}

// хорошо
if (isValid) {
  // ...
}

// плохо
if (name) {
  // ...
}

// хорошо
if (name !== '') {
  // ...
}

// плохо
if (collection.length) {
  // ...
}

// хорошо
if (collection.length > 0) {
  // ...
}
```


