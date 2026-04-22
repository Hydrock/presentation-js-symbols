# Слайд 4: Symbol как способ скрытия данных

## "Псевдо-приватные" поля

Symbol позволяет создавать свойства, которые не будут видны при обычном доступе к объекту, но при этом не являются настоящими приватными полями.

```javascript
const secret = Symbol();
const user = {
  name: 'Aleksei',
  [secret]: 'hidden'
};
```

## Почему это не полноценный private

Symbol не обеспечивает настоящую приватность, так как:

1. Свойства можно получить через Object.getOwnPropertySymbols()
2. Символы могут быть доступны другим частям кода
3. Нет механизма для ограничения доступа

```javascript
const secret = Symbol();
const user = {
  name: 'Aleksei',
  [secret]: 'hidden'
};

console.log(Object.getOwnPropertySymbols(user)); // [Symbol()]
console.log(user[secret]); // 'hidden'
```

Это делает их "псевдо-приватными" - скрытыми от обычного использования, но не защищенными от доступа.