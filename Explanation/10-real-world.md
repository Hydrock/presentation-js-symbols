# Слайд 8: Symbols в реальных библиотеках

## React

React использует символы для определения типов элементов:

```javascript
// Внутреннее представление React элемента
const element = {
  $$typeof: Symbol.for('react.element'),
  type: 'div',
  props: {}
};
```

## Node.js

Node.js использует Symbol для кастомной отладки:

```javascript
const util = require('util');

const obj = {
  [util.inspect.custom]() {
    return 'Custom inspection result';
  }
};

console.log(util.inspect(obj)); // 'Custom inspection result'
```

## Redux

Redux использует символы для внутренних action types:

```javascript
// Внутренние action types в Redux
const ActionTypes = {
  INIT: '@@redux/INIT',
  REPLACE: '@@redux/REPLACE',
  // ... другие
};
```

Эти примеры показывают, как символы используются для создания уникальных идентификаторов и скрытия внутренней логики.