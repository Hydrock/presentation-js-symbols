# Слайд 7.2: Symbol.toPrimitive

## Когда вызывается

Symbol.toPrimitive вызывается при преобразовании объекта в примитив по следующим правилам:
- При использовании оператора + (когда объект находится справа от +)
- При использовании в шаблонных строках ${obj}
- При сравнении с примитивами (obj == 1)

## Пример использования

```javascript
const obj = {
  [Symbol.toPrimitive](hint) {
    if (hint === 'number') return 42;
    if (hint === 'string') return 'hello';
    return true; // по умолчанию
  }
};

console.log(+obj); // 42
console.log(`${obj}`); // "hello"
console.log(obj == 1); // true
```

## Поведение по умолчанию

Если Symbol.toPrimitive не определен, JavaScript использует другие методы:
- Для числового преобразования: valueOf()
- Для строкового преобразования: toString()