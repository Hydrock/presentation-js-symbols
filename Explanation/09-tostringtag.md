# Слайд 7.3: Symbol.toStringTag

## Назначение

Symbol.toStringTag используется для настройки вывода метода Object.prototype.toString.call().

## Пример использования

```javascript
const obj = {
  [Symbol.toStringTag]: 'CustomObject'
};

console.log(Object.prototype.toString.call(obj));
// [object CustomObject]

// Без Symbol.toStringTag:
const obj2 = {};
console.log(Object.prototype.toString.call(obj2));
// [object Object]
```

## Встроенные примеры

Некоторые встроенные объекты уже используют Symbol.toStringTag:

```javascript
console.log(Object.prototype.toString.call([])); // [object Array]
console.log(Object.prototype.toString.call(new Map())); // [object Map]
console.log(Object.prototype.toString.call(new Set())); // [object Set]
```

## Практическое применение

Полезно для создания более информативных сообщений об ошибках и отладки.