```typescript
// Bad practice
function u(p: Product[]) {
  // Non-descriptive function name and parameter
  for (let i = 0; i < p.length; i++) {
    // Requires mental mapping
    console.log(p[i]);
  }
}

// Good practice
function printProducts(products: Product[]) {
  // Use descriptive function names
  products.forEach((product) => console.log(product)); // Use higher-order functions instead of loops
}

// Function that does one thing
function calculateTotalPrice(cart: Cart): number {
  // Use names that reveal intent
  return cart.products.reduce((total, product) => total + product.price, 0); // Use higher-order functions instead of loops
}
```

in this example:

- Use descriptive function names: printProducts and calculateTotalPrice are examples of descriptive function names. They clearly indicate what the function does.

- Functions should do one thing: calculateTotalPrice is a good example of a function that does one thing. It calculates the total price of all products in a cart.

- Use higher-order functions instead of loops: Both printProducts and calculateTotalPrice use higher-order functions (forEach and reduce) instead of loops. This makes the code more concise and easier to understand.

- Use names that reveal intent: calculateTotalPrice is a good example of a function name that reveals intent. It's clear that this function is expected to calculate and return the total price of all products in a cart.
