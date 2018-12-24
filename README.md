# Predicting Method Returns

## Questions

```js
class Car {
  constructor(make, model, owner, gas = 100) {
    this.make = make;
    this.model = model;
    this.owner = owner;
    this.gas = gas;
  }

  vroom() {
    this.gas -= 3;
    return `The ${this.make} ${this.model} goes VROOOOOOOOOOOOOM`;
  }

  getGas(gasAmount) {
    if (this.gas + gasAmount > 100) {
      this.gas = 100;
    } else {
      this.gas += gasAmount;
    }
    return `The gas tank is now at ${this.gas}`;
  }
}

let car = new Car('Honda', 'Civic', 'Emily Howell', 58);
```

1.  Given the `class` above and the instance `car`, what would `vroom` return?

2.  What would `car.getGas(50)` return?

```js
class Triangle {
  constructor(a, b, c) {
    if (this.isValid(a, b, c)) {
      this.a = a;
      this.b = b;
      this.c = c;
    } else {
      throw new Error('Not a valid triangle');
    }
  }

  isValid(a = this.a, b = this.b, c = this.c) {
    if (a + b <= c || a + c <= b || b + c <= a) {
      return false;
    } else {
      return true;
    }
  }

  isRightTriangle() {
    let a = this.a;
    let b = this.b;
    let c = this.c;
    let hypotenuse = Math.max(a, b, c);

    if (hypotenuse == a) {
      return this.checkPythagorean(b, c, a);
    }
    if (hypotenuse == b) {
      return this.checkPythagorean(a, c, b);
    }
    if (hypotenuse == c) {
      return this.checkPythagorean(a, b, c);
    }

    return false;
  }

  checkPythagorean(sideA, sideB, hypotenuse) {
    return sideA * sideA + sideB * sideB == hypotenuse * hypotenuse;
  }
}
```

3.  What will `this.isValid(1,2,3)` return?

4.  What about `this.isValid(4,5,6)`?

```js
let triangle = new Triangle(3, 4, 5);
```

5.  Given the instance above, what will be the result of `triangle.isRightTriangle()`?

```js
triangle.a = 1;
```

6.  The `a` property has changed for this instance. What is the result of `triangle.isValid()`?
