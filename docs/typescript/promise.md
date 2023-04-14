---
layout: home
parent: Typescript
title: Promise
---

# Promise

A Promise is a JavaScript object representing the eventual completion (or failure) of an asynchronous operation, and its resulting value. 

It is a way to handle asynchronous code in a more synchronous way, by allowing you to register callbacks that will be called when the asynchronous operation completes.

## Structure

States:

- **Pending**: The initial state, when the promise is neither fulfilled nor rejected.
- **Fulfilled**: The state when the promise is successfully fulfilled with a value.
- **Rejected**: The state when the promise is rejected with an error.

Methods:

- **then()**: The then() method is used to register a callback function that will be called when the Promise is successfully fulfilled.
- **catch()**: The catch() method is used to register a callback function that will be called when the Promise is rejected with an error.

## Example

```javascript
const myPromise = new Promise((resolve, reject) => {
  // Perform some asynchronous operation
  setTimeout(() => {
    const result = Math.random();
    if (result < 0.5) {
      resolve(result); // Fulfill the Promise
    } else {
      reject(new Error('Promise rejected')); // Reject the Promise with an error
    }
  }, 1000);
});

// Use the Promise
myPromise.then((result) => {
  console.log(`Promise fulfilled with result ${result}`);
}).catch((error) => {
  console.error(`Promise rejected with error ${error}`);
});
```
