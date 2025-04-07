# TwoTasks
Two easy tasks before you apply for an interview

1. Задача: не змінюючи логіки, змінити структуру коду, щоби вона відповідала принципу DRY:

function iterator(to, from, apply) {
    var keys = Object.keys(from);
    var i;
    var key;
    for (i=0, i < keys.length, i++) {
        key = keys[i];
        to[key] = apply(from, key)
    }
    return to;
}

ctx.prototype.__applyStyleState = function (styleState) { iterator(this, styleState, (obj, key) => obj[key]) };

ctx.prototype.__setDefaultStyles = function () { iterator(this, STYLES, (obj, key) => obj[key].canvas) };

ctx.prototype.__getStyleState = function () { return iterator({}, STYLES, (obj, key) => this[key]) };

2. Друга задача:

const multiply = (a, b, c) => a * b * c;
const add = (a, b, c, d, e) => a + b + c + d + e;

const curry = (f) => {
  return function loop(...args) {
    if (args.length == f.length) {
      return f(...args);
    } else {
      return (...nextArgs) => loop(...args.concat(nextArgs));
    }
  };
};

curry(add)(1)(2)(3)(4)(5) == add(1,2,3,4,5) // should be true
curry(multiply)(1)(2)(3) == multiply(1,2,3) // should be true

Гарного дня! :)
