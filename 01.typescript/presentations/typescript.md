@title[TypeScript]
## TypeScript

+++

![Alt text](01.typescript/images/image3.png)
![Alt text](01.typescript/images/image2.png)

+++

```javascript
function greeter(person: string) {
    return "Hello, " + person;
}

let user = "Jane User";

document.body.innerHTML = greeter(user);
===========================
function greeter(person) {
    return "Hello, " + person;
}

let user = "Jane User";

document.body.innerHTML = greeter(user);

```
@[1-7](function parameter type)
@[9-16](compile result)

+++

```javascript
function greeter(person: string) {
    return "Hello, " + person;
}

let user = [0, 1, 2];

document.body.innerHTML = greeter(user);
```
```
error TS2345: Argument of type 'number[]' is not assignable to parameter of type 'string'.
```