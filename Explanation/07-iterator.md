# Слайд 7.1: Symbol.iterator

## Использование Symbol.iterator

Symbol.iterator определяет поведение итерации для объектов, позволяя использовать их в циклах for...of.

```javascript
const obj = {
  *[Symbol.iterator]() {
    yield 1;
    yield 2;
  }
};

for (const value of obj) {
  console.log(value); // 1, затем 2
}
```

## Создание итерируемого объекта

```javascript
const iterable = {
  [Symbol.iterator]() {
    let step = 0;
    const maxSteps = 3;
    return {
      next() {
        if (step < maxSteps) {
          step++;
          return { value: step, done: false };
        }
        return { value: undefined, done: true };
      }
    };
  }
};
```