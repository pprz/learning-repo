Use getters and setters

```js
// Bad practice
class User {
   age: number; // Public property
}

const user = new User();
user.age = 20; // Directly modifying a public property

// Good practice
class User {
   private _age: number; // Private property

   get age(): number { // Getter
       return this._age;
   }

   set age(value: number) { // Setter
       if (value >= 0) {
           this._age = value;
       }
   }
}

const user = new User();
user.age = 20; // Using setter to modify a private property
```

Make objects have private/protected members

```js
// Bad practice
class User {
    age: number; // Public property
}

// Good practice
class User {
    private age: number; // Private property
}
```

Objects hide their data behind abstractions

```js
// Bad practice
class User {
    age: number; // Public property

    isAdult(): boolean {
        return this.age >= 18; // Using internal data directly
    }
}

// Good practice
class User {
    private age: number; // Private property

    isAdult(): boolean {
        return this.getAge() >= 18; // Using abstraction to access internal data
    }

    private getAge(): number {
        return this.age;
    }
}
```

Objects expose behavior and hide data

```js
// Bad practice
class User {
    age: number; // Exposing data
}

// Good practice
class User {
    private age: number; // Hiding data

    isAdult(): boolean { // Exposing behavior
        return this.age >= 18;
    }
}
```

Prefer data structures

```js
// Bad practice
class User {
    private age: number; // Hiding data

    isAdult(): boolean { // Exposing behavior
        return this.age >= 18;
    }
}

// Good practice
interface User { // Data structure
    age: number;
}

function isAdult(user: User): boolean { // Function that operates on a data structure
    return user.age >= 18;
}
```

Avoid monolithic structures

```js
// Bad practice
class User {
  name: string;
  age: number;
  address: string;
  // ... many more properties
}

// Good practice
interface User {
  name: string;
  age: number;
}

interface Address {
  street: string;
  city: string;
  // ... other address properties
}
```
