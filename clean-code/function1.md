```typescript
// Bad practice
function a(n: string, e: string, a: string = "OK", c: boolean = true) {
  // Non-descriptive function name and parameters
  // ...
}

// Good practice
function createDialogBox(options: DialogOptions) {
  // Function names should say what they do
  const { title, body, buttonText = "OK", cancellable = true } = options;
  // ...
}

// Function that does one thing
function isUserActive(user: User): boolean {
  // Functions should only be one level of abstraction
  return user.isActive; // Avoids unnecessary temporary variables
}

// Remove duplicate code
function calculateTotalPrice(cart: Cart): number {
  // Use names that reveal intent
  return cart.products.reduce((total, product) => total + product.price, 0); // Use iterators and generators
}

// Set default objects with Object.assign or destructuring
function createProduct(options: Partial<Product> = {}) {
  const defaultOptions = {
    name: "Default Name",
    price: 100,
    isAvailable: true,
  };
  const finalOptions = { ...defaultOptions, ...options }; // Set default objects with Object.assign or destructuring
  // ...
}

// Don't use flags as function parameters
function createInvoice(product: Product, isDiscounted: boolean) {
  // Don't use flags as function parameters
  if (isDiscounted) {
    // ...
  } else {
    // ...
  }
}

// Avoid Side Effects (part 1)
let name = "John Doe"; // Avoid writing to global functions
function setName(newName: string) {
  name = newName; // This is a side effect
}

// Avoid Side Effects (part 2)
function createInvoice(product: Product) {
  product.price = 100; // This is a side effect
}

// Favor functional programming over imperative programming
let activeUsers = []; // Avoid Side Effects (part 1)
for (let i = 0; i < users.length; i++) {
  // Favor functional programming over imperative programming
  if (users[i].isActive) {
    activeUsers.push(users[i]);
  }
}

// Encapsulate conditionals
if (user.age >= 18 && user.isActive) {
  // Encapsulate conditionals
  // ...
}

// Avoid negative conditionals
if (!user.isInactive) {
  // Avoid negative conditionals
  // ...
}

// Avoid conditionals
function getFee(isMember: boolean) {
  // Avoid conditionals
  return isMember ? 0.1 : 0.2;
}

// Avoid type checking
function combine(a: any, b: any) {
  // Avoid type checking
  if (typeof a === "string" || typeof b === "string") {
    return a.toString() + b.toString();
  }
  return a + b;
}

// Don't over-optimize
for (let i = 0; i < 1000000; i++) {
  // Don't over-optimize
  // ...
}

// Remove dead code
function oldFunction() {
  // Remove dead code
  // ...
}
```
