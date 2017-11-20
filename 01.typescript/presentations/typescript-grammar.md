@title[TypeScript Grammar]
## TypeScript Grammar

+++
### Type annotations
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

+++
### Interfaces
```javascript
interface Person {
    firstName: string;
    lastName: string;
}

function greeter(person: Person) {
    return "Hello, " + person.firstName + " " + person.lastName;
}

let user = { firstName: "Jane", lastName: "User" };

document.body.innerHTML = greeter(user);
```

+++
### Classes
```javascript
class Student {
    fullName: string;
    constructor(public firstName: string, public middleInitial: string, public lastName: string) {
        this.fullName = firstName + " " + middleInitial + " " + lastName;
    }
}

interface Person {
    firstName: string;
    lastName: string;
}

function greeter(person : Person) {
    return "Hello, " + person.firstName + " " + person.lastName;
}

let user = new Student("Jane", "M.", "User");

document.body.innerHTML = greeter(user);
```

+++
### React with TypeScript
```javascript
// src/components/Hello.tsx

import * as React from 'react';

export interface Props {
  name: string;
  enthusiasmLevel?: number;
}

function Hello({ name, enthusiasmLevel = 1 }: Props) {
  if (enthusiasmLevel <= 0) {
    throw new Error('You could be a little more enthusiastic. :D');
  }

  return (
    <div className="hello">
      <div className="greeting">
        Hello {name + getExclamationMarks(enthusiasmLevel)}
      </div>
    </div>
  );
}

export default Hello;

// helpers

function getExclamationMarks(numChars: number) {
  return Array(numChars + 1).join('!');
}
```

+++
### Tutorial
 - [Official Documentation](https://www.typescriptlang.org/docs/handbook/basic-types.html)
 - [Migration Guide](https://www.typescriptlang.org/docs/handbook/migrating-from-javascript.html)
 - [Converting JavaScript/React to TypeScript](https://github.com/Microsoft/TypeScript-React-Conversion-Guide#typescript-react-conversion-guide)