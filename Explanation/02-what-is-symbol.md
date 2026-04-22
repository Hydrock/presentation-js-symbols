# Слайд 2: Что такое Symbol

## Примитивный тип

Symbol - это примитивный тип данных в JavaScript (как string, number, boolean), а не объект.

## Уникальность по определению

Каждый Symbol, созданный с помощью функции Symbol(), уникален, даже если у них одинаковые описания.

```javascript
const s1 = Symbol('id');
const s2 = Symbol('id');
console.log(s1 === s2); // false
```

## Невозможность неявного преобразования в строку

Symbol нельзя неявно преобразовать в строку, что делает его действительно уникальным ключом.

```javascript
const sym = Symbol('test');
console.log(sym.toString()); // Symbol(test)
console.log(String(sym)); // Symbol(test)
// Но: console.log(sym + ''); // TypeError
```