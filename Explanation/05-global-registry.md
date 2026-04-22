# Слайд 5: Глобальный реестр символов

## Symbol.for и Symbol.keyFor

Symbol.for() позволяет создавать символы, которые будут сохранены в глобальном реестре и могут быть повторно использованы.

```javascript
const s1 = Symbol.for('id');
const s2 = Symbol.for('id');
console.log(s1 === s2); // true
```

## Когда нужен shared symbol

Глобальный реестр полезен, когда нужно использовать один и тот же символ в разных частях приложения или библиотеки.

```javascript
// В библиотеке
const MY_SYMBOL = Symbol.for('mylib.mySymbol');

// В приложении
const MY_SYMBOL = Symbol.for('mylib.mySymbol');

// Они будут одинаковыми
console.log(MY_SYMBOL === Symbol.for('mylib.mySymbol')); // true
```

## Контраст между Symbol() и Symbol.for()

- Symbol() → всегда новый уникальный символ
- Symbol.for() → возвращает символ из реестра или создает новый, если его там нет