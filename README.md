# JavaScript Interview Questions

It's for me.

## Table of Contents

- [Quoted](#1.0)
- [My own](#2.0)
- [Answers](#answers)

<a name='1.0'/>

## 1.0 Quoted

<a name='1.1'/>

### 1.1 `typeof` operator
What is a potential pitfall with using `typeof bar === "object"` to determine if `bar` is an object? How can this pitfall be avoided?

[See Answer](#a1.1)

---

<a name='1.2'/>

### 1.2
What will the code below output to the console and why?

```javascript
(function(){
  var a = b = 3;
})();

console.log("a defined? " + (typeof a !== 'undefined'));
console.log("b defined? " + (typeof b !== 'undefined'));
```

[See Answer](#a1.2)

---

<a name='1.3'>

### 1.3
What will the code below output to the console and why?

```javascript
var myObject = {
    foo: "bar",
    func: function() {
        var self = this;
        console.log("outer func:  this.foo = " + this.foo);
        console.log("outer func:  self.foo = " + self.foo);
        (function() {
            console.log("inner func:  this.foo = " + this.foo);
            console.log("inner func:  self.foo = " + self.foo);
        }());
    }
};
myObject.func();
```

[See Answer](#a1.3)

---

<a name='1.4'/>

### 1.4

What is the significance of, and reason for, wrapping the entire content of a JavaScript source file in a function block?

[See Answer](#a1.4)

---

<a name='1.5'/>

### 1.5

What is the significance, and what are the benefits, of including 'use strict' at the beginning of a JavaScript source file?

[See Answer](#a1.5)

---

<a name='1.6'/>

### 1.6

Consider the two functions below. Will they both return the same thing? Why or why not?

```javascript
function foo1()
{
  return {
      bar: "hello"
  };
}

function foo2()
{
  return
  {
      bar: "hello"
  };
}
```

[See Answer](#a1.6)

---

<a name='1.7'/>

### 1.7

What is NaN? What is its type? How can you reliably test if a value is equal to NaN?

[See Answer](#a1.7)

---

<a name='1.8'/>

### 1.8

What will the code below output? Explain your answer.
```javascript
console.log(0.1 + 0.2);
console.log(0.1 + 0.2 == 0.3);
```

[See Answer](#a1.8)

---

<a name='2.0'/>

## 2.0 My own

<a name='2.1'/>

### 2.1

[See Answer](#a2.1)

---

## Answers

<a name='a1.1'/>

### A1.1
`typeof` operator in JavaScript thinks that `null` variable is `'object'`. Therefore, if `bar` is `null`, `true` is returned.
`typeof bar === "object" && bar !== null` is a solution.

[Back to Question](#1.1)

---

<a name='a1.2'/>

### A1.2
`a defined? false`<br>
`b defined? true`

Because `b` is in the global area, the output of 2nd console is `true`. In strict mode that statement will make a runtime error of `ReferenceError`.

[JSbin](http://jsbin.com/pakicav/edit?js,console)

[Back to Question](#1.2)

---

<a name='a1.3'/>

### A1.3
`outer func:  this.foo = bar`<br>
`outer func:  self.foo = bar`<br>
`inner func:  this.foo = undefined`<br>
`inner func:  self.foo = bar`

The context of inner function is global object, that is window. Because there is not a `foo` variable in window, `this.foo` is `undefined`. The `self` variable, is closure to outer function, has a reference to the scope of outer function, so it can access to `foo`.

[JSbin](http://jsbin.com/javove/edit?js,console)

[Back to Question](#1.3)

---

<a name='a1.4'/>

### A1.4

It is important to avoid the namespace collision between different libs and modules. Most popular libs use this way to provie a private namespace.

[Back to Question](#1.4)

---

<a name='a1.5'/>

### A1.5

It prevents accidental global variables. a undeclared variable don't become a global variable. Referencing `this` value of `null` or `undefined` throws an error. It disallow duplicate property names or duplicate argument values. Makes `eval()` safer. Do not delete non-configurable properties.

[Back to Question](#1.5)

---

<a name='a1.6'/>

### 1.6

`foo1` returns object(`{bar: "hello"}`) but `foo2` returns `undefined`, because in `foo2` a semicolon is inserted automactically after return statement.

[Back to Question](#1.6)

---

<a name='a1.7'/>

### 1.7

`NaN` means not to evluate as Number. It results from an operation could not be perforemd because one of the operands was non-numeric. It is used to test a value by Number.isNaN() function or `value !== value`.

[Back to Question](#1.7)

---

<a name='a1.8'/>

### 1.8

Numbers in JavaScript are all floating point precision.

[JSbin](http://jsbin.com/vezodop/edit?js,console)

[Back to Question](#1.8)

---

<a name='a2.1'/>

### 2.1

[Back to Question](#2.1)

---
