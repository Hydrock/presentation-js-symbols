# Слайд 13: Демонстрация

## Создание iterable объекта

```javascript
const iterableObj = {
  *[Symbol.iterator]() {
    yield 1;
    yield 2;
    yield 3;
  }
};

for (const value of iterableObj) {
  console.log(value); // 1, 2, 3
}
```

## Переопределение toPrimitive

```javascript
const obj = {
  [Symbol.toPrimitive](hint) {
    if (hint === 'number') return 42;
    if (hint === 'string') return 'hello';
    return true;
  }
};

console.log(+obj); // 42
console.log(`${obj}`); // "hello"
console.log(obj == 1); // true
```

## Показать скрытые свойства

```javascript
const secret = Symbol('secret');
const user = {
  name: 'Aleksei',
  [secret]: 'hidden'
};

console.log(Object.getOwnPropertySymbols(user)); // [Symbol(secret)]
console.log(user[secret]); // 'hidden'
```

## Сравнить Symbol() vs Symbol.for()

```javascript
const sym1 = Symbol('id');
const sym2 = Symbol('id');
console.log(sym1 === sym2); // false

const sym3 = Symbol.for('id');
const sym4 = Symbol.for('id');
console.log(sym3 === sym4); // true
```