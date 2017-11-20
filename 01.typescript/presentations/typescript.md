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


function greeter(person) {
    return "Hello, " + person;
}

let user = "Jane User";

document.body.innerHTML = greeter(user);

```
@[1-7](function parameter type)
@[10-18](compile result)