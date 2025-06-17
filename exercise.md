---

### ✅ **TypeScript Exercises – Part 1**

#### 🔹 **Exercise 1: Type Annotations**

```ts
// Declare the following variables with the correct types:

let name = "Ahmed";
let age = 25;
let isStudent = true;
```

---

#### 🔹 **Exercise: Union Types**

```ts
// Declare a variable that can be either a string or a number:

let id; // Example: id = "abc123" or id = 101
```

---

#### 🔹 **Exercise: Function with Union Parameter**

```ts
// Write a function that accepts a value (string or number)
// and prints the type of the value:

function printType(value) {
  // ...
}
```

---

#### 🔹 **Exercise: Create a `type` for a Person**

```ts
// Create a `type` called Person with:
// - name: string
// - age: number
// - isAdmin: boolean

// Then declare a variable of that type
```

---

#### 🔹 **Exercise: Create an Interface for a Product**

```ts
// Create an interface called Product with:
// - id: number
// - name: string
// - price: number
// - inStock: boolean

// Then create a product object using that interface
```

---

#### 🔹 **Exercise: Type vs Interface**

```ts
// Create a `type` and an `interface` with the same structure:

type A = { name: string }
interface B { name: string }

// Try to extend both and notice the differences
```

---

#### 🔹 **Exercise: Extending Types and Interfaces**

```ts
// Try extending both a type and an interface:

type User = { name: string }
type Admin = User & { isAdmin: boolean }

interface Person { name: string }
interface Manager extends Person { teamSize: number }
```

