# Слайд 11: Альтернативы

## #private поля (классы)

В современном JavaScript есть приватные поля классов:

```javascript
class MyClass {
  #privateField = 'secret';
  
  getPrivate() {
    return this.#privateField;
  }
}
```

## WeakMap

Для хранения приватных данных можно использовать WeakMap:

```javascript
const privateData = new WeakMap();

class MyClass {
  constructor() {
    privateData.set(this, 'secret');
  }
  
  getPrivate() {
    return privateData.get(this);
  }
}
```

## Обычные строки (если не нужна уникальность)

Если уникальность не требуется, обычные строки могут быть более подходящим выбором:

```javascript
const key = 'myProperty'; // Просто строка
const obj = {
  [key]: 'value'
};
```

Каждый подход имеет свои преимущества и недостатки, выбор зависит от конкретной задачи.