```typescript
// Bad practice
let a1; // Non-descriptive variable name
let daysSinceCreation; // Unnecessary context
let myArray; // Unnecessary "my" prefix

// Good practice
let products: Product[]; // Use meaningful and pronounceable variable names
let isProductAvailable: boolean; // Use names that reveal intent
let maxProductPrice: number = 500; // Use searchable names

// Function that uses default arguments instead of short circuiting or conditionals
function createProduct(props: {
  name: string;
  description: string;
  price: number = 100;
}) {
  const { name, description, price } = props; //props should be less
}
```

In this example:

1. Use meaningful and pronounceable variable names: products, isProductAvailable, and maxProductPrice are all examples of meaningful and pronounceable variable names. They clearly indicate what values they hold.

2. Use names that reveal intent: isProductAvailable is a good example of a variable name that reveals intent. It's clear that this variable is expected to be a boolean value that indicates whether a product is available.

3. Use searchable names: maxProductPrice is a searchable name. If someone wants to find all places in the code where the maximum product price is used, they can simply search for maxProductPrice.

4. Use default arguments instead of short circuiting or conditionals: The createProduct function uses default arguments for price and isAvailable. This is clearer and cleaner than using short circuiting or conditionals to assign default values.

5. Avoid adding unnecessary context: In the bad practice example, daysSinceCreation has unnecessary context. If we are working within a class or module named Product, it's clear that days would refer to the number of days since the product was created.

6. Avoid mental mapping: In the bad practice example, a1 is a poor choice for a variable name because it requires mental mapping. It's not clear what a1 stands for unless you keep a mental note that a1 stands for "array 1".

7. Don't add unneeded prefixes: In the bad practice example, myArray has an unneeded prefix "my". Just array is clear and sufficient.
