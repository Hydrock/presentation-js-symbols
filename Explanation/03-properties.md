# Слайд 3: Основные свойства Symbol

## Уникальность

Каждый Symbol уникален, даже если они созданы с одинаковыми описаниями.

```javascript
const sym1 = Symbol('key');
const sym2 = Symbol('key');
console.log(sym1 === sym2); // false
```

## Не перечисляется в обычных циклах

Symbol не будет отображаться в циклах for...in и Object.keys(), что делает их скрытыми для обычного доступа.

```javascript
const key = Symbol('secret');
const obj = {
  [key]: 123,
  name: 'test'
};

console.log(Object.keys(obj)); // ['name']
console.log(Object.getOwnPropertyNames(obj)); // ['name']
console.log(Object.getOwnPropertySymbols(obj)); // [Symbol(secret)]
```

## Используется как ключ объекта

Symbol может быть использован как ключ в объектах и классах для создания уникальных свойств.

```javascript
const key = Symbol('secret');
const obj = {
  [key]: 123
};
```