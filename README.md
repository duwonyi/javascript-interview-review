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

<a name='2.0'/>

## 2.0 My own

<a name='2.1'/>

### 2.1

[See Answer](#a2.1)

---

## Answers

<a name='a1.1'/>

### 1.1
`typeof` operator in JavaScript thinks that `null` variable is `'object'`. Therefore, if `bar` is `null`, `true` is returned.
`typeof bar === "object" && bar !== null` is a solution.

[Back to Question](#1.1)

---

<a name='a1.2'/>

### 1.2
`a defined? false`<br>
`b defined? true`

Because `b` is in the global area, the output of 2nd console is `true`. In strict mode that statement will make a runtime error of `ReferenceError`.

[Back to Question](#1.2)

---

<a name='a2.1'/>

### 2.1

[Back to Question](#2.1)

---
