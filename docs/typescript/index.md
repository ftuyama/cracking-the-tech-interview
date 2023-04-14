---
layout: home
title: Typescript
---

# Typescript

- **Type Annotations**: TypeScript is a typed language, which means that variables and functions can have types. Type annotations help catch errors at compile-time and make code more self-documenting.
- **Type Inference**: TypeScript uses type inference to automatically infer types when possible. This reduces the amount of code that developers need to write, while still catching errors at compile-time.
- **Type Guards**: TypeScript has type guards, which are functions that can determine the type of an object at runtime. Type guards can be used to write code that is more expressive and type-safe.
- **Interfaces**: TypeScript has interfaces, which allow developers to define the shape of an object. This can be useful when working with complex data structures or when creating APIs.
- **Classes**: TypeScript has classes, which are similar to classes in object-oriented programming languages like Java or C#. Classes can have properties and methods, and can be extended and inherited from.
- **Namespaces**: TypeScript has namespaces, which allow developers to organize code into logical groups. Namespaces can be nested, and can be used to avoid naming collisions.
- **Modules**: TypeScript has modules, which allow developers to organize code into reusable and sharable units. Modules can be imported and exported, and can be used to create libraries or to split large applications into smaller parts.
- **Enums**: TypeScript has enums, which allow developers to define a set of named constants. This can be useful when working with fixed sets of values.
- **Generics**: TypeScript has generics, which allow developers to create reusable components that can work with a variety of types. This can be useful when working with collections or algorithms.
- **Decorators**: TypeScript has decorators, which are functions that can modify the behavior of classes, methods, or properties. Decorators can be used to add metadata, to modify behavior, or to provide additional functionality.

## Async/Await

```typescript
async function fetchUserData(userId: number): Promise<User> {
  const response = await fetch(`https://api.example.com/users/${userId}`);
  const userData = await response.json();
  return userData;
}

async function main() {
  try {
    const user = await fetchUserData(123);
    console.log(`User: ${user.name}, Email: ${user.email}`);
  } catch (error) {
    console.error(error);
  }
}

main();
```
