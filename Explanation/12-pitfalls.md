# Слайд 10: Подводные камни

## ❗ Не видны в JSON.stringify

Символы игнорируются при сериализации в JSON, что может привести к потере данных.

```javascript
const obj = {
  name: 'test',
  [Symbol('key')]: 'value'
};

console.log(JSON.stringify(obj)); // {"name":"test"}
// Символ исчез!
```

## ❗ Не копируются через Object.assign (частично)

Object.assign игнорирует символы при копировании свойств.

```javascript
const sym = Symbol('key');
const source = { [sym]: 'value' };
const target = {};

Object.assign(target, source);
console.log(target); // {}
// Символ не скопирован
```

## ❗ Трудно дебажить

Символы не отображаются в обычных циклах и могут быть трудны для отладки.

## ❗ Ложное ощущение приватности

Символы не обеспечивают настоящую приватность - их можно получить через Object.getOwnPropertySymbols().