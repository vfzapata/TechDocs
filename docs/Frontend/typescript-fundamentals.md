## TypeScript Fundamentals
### What is TypeScript and Why It Is Used

TypeScript is a <strong>strongly-typed superset of JavaScript</strong> developed by Microsoft. It adds static typing and other powerful features on top of JavaScript, making it easier to catch errors during development rather than at runtime.

TypeScript is compiled (or transpiled) into plain JavaScript, so it can run in any environment where JavaScript runs—browsers, Node.js, etc.

### Why Use TypeScript?

- <strong>Type safety:</strong> Catch bugs at compile time before they break your application.
- <strong>Better tooling:</strong> Autocompletion, refactoring, and documentation are more powerful with types.
- <strong>Scalability:</strong> Makes maintaining large codebases easier by enforcing contracts between components.
- <strong>Readability:</strong> Types serve as documentation, making code easier to understand.

### TypeScript Types

TypeScript comes with several basic types that help ensure variables are used correctly.

```
// String
let firstName: string = "Jhon Doe";

// Number
let age: number = 34;

// Boolean
let isDeveloper: boolean = true;

// Arrays
let numbers: number[] = [1, 2, 3];
let names: Array<string> = ["Alice", "Bob", "Charlie"];

// Any (avoid when possible, disables type checking)
let randomValue: any = "Could be anything";
randomValue = 42; // Allowed, but not type-safe

// Void (for functions that return nothing)
function logMessage(message: string): void {
  console.log(message);
}

// Never (for functions that never return)
function throwError(errorMsg: string): never {
  throw new Error(errorMsg);
}
```

### Enums

Enums allow you to define a set of named constants. They make your code more readable and less error-prone by avoiding the use of "magic numbers" or strings.

```
enum Role {
  Admin,
  User,
  Guest
}

let currentRole: Role = Role.Admin;

if (currentRole === Role.Admin) {
  console.log("You have admin privileges!");
}

// Enums can also be string-based
enum Direction {
  Up = "UP",
  Down = "DOWN",
  Left = "LEFT",
  Right = "RIGHT"
}

let move: Direction = Direction.Left;
console.log(move); // Output: LEFT
```

### Interfaces

Interfaces are a way to define the shape of an object. They are extremely useful for describing complex objects and enforcing consistency across your code.

```
interface Person {
  name: string;
  age: number;
  isEmployed?: boolean; // optional property
}

const user: Person = {
  name: "Jhon Doe",
  age: 34,
};

function greet(person: Person): void {
  console.log(`Hello, ${person.name}!`);
}

greet(user);
```

Interfaces can also describe function types or classes:

```
interface MathOperation {
  (a: number, b: number): number;
}

const add: MathOperation = (x, y) => x + y;
const subtract: MathOperation = (x, y) => x - y;
```

### Advantages and Disadvantages of TypeScript

### ✅ Advantages
- Early Error Detection: Find and fix errors before runtime.
- Better IDE Support: Autocomplete, type inference, and refactoring tools work much better.
- Scalability: Ideal for large projects and teams.
- Self-Documentation: Types make code more understandable.

### ❌ Disadvantages
- Learning Curve: Developers need to learn new syntax and concepts.
- Compilation Step: Requires a build step before running.
- Initial Setup: Requires configuration (tsconfig.json) and integration with build tools.
- Overhead for Small Projects: Might feel too heavy for quick prototypes or small scripts.
