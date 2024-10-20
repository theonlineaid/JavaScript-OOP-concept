In JavaScript, subclasses can be created using the `class` syntax, which allows you to extend a base (or parent) class. The `super` keyword is used to call the constructor and methods of the parent class from within the subclass. This allows the subclass to inherit properties and methods from the parent class, enabling code reuse and a more structured way to handle objects.

### Key Concepts

- **Inheritance**: The ability for a class (subclass) to inherit properties and methods from another class (superclass).
- **`super` Keyword**: Used to call the constructor of the parent class and access its properties and methods.

### Example of Subclass and Super Calls

Here’s a detailed example that demonstrates how to use subclasses and `super` calls in JavaScript:

#### Parent Class

```javascript
class Animal {
    constructor(name, type) {
        this.name = name; // Property to store the name of the animal
        this.type = type; // Property to store the type of the animal
    }

    makeSound() {
        console.log(`${this.name} makes a sound.`);
    }
}
```

#### Subclass

```javascript
class Dog extends Animal { // Dog is a subclass of Animal
    constructor(name, breed) {
        super(name, 'Dog'); // Call the parent class constructor
        this.breed = breed; // Additional property specific to Dog
    }

    // Overriding the makeSound method
    makeSound() {
        console.log(`${this.name}, the ${this.breed}, barks.`);
    }

    fetch() {
        console.log(`${this.name} is fetching the ball!`);
    }
}
```

### Usage Example

```javascript
// Creating an instance of the Dog subclass
const myDog = new Dog('Buddy', 'Golden Retriever');

// Accessing properties
console.log(myDog.name); // Output: Buddy
console.log(myDog.type); // Output: Dog
console.log(myDog.breed); // Output: Golden Retriever

// Calling methods
myDog.makeSound(); // Output: Buddy, the Golden Retriever, barks.
myDog.fetch(); // Output: Buddy is fetching the ball!
```

### Explanation of Code

1. **Animal Class**: 
   - The `Animal` class has a constructor that initializes the `name` and `type` properties.
   - It also has a method `makeSound` that logs a generic sound message.

2. **Dog Class**:
   - The `Dog` class extends the `Animal` class, making it a subclass.
   - Inside its constructor, it calls the parent class constructor using `super(name, 'Dog')`, passing the `name` and a fixed `type` ('Dog').
   - The `Dog` class adds an additional property `breed`.
   - It overrides the `makeSound` method to provide a more specific implementation that includes the dog's breed.
   - It also has a new method `fetch`.

### Key Points

- **Calling `super()`**: Always call `super()` in the constructor of a subclass before using `this`. This is necessary to initialize the properties inherited from the parent class.
- **Method Overriding**: The subclass can override methods from the parent class to provide specific functionality.
- **Accessing Parent Methods**: You can still call parent methods from the subclass using `super.methodName()`. For example:

```javascript
class Dog extends Animal {
    makeSound() {
        super.makeSound(); // Call the parent method
        console.log(`${this.name} barks loudly!`);
    }
}
```

### Conclusion

Using subclasses and the `super` keyword allows you to create a clear and structured hierarchy in your code, promoting code reuse and encapsulation. This is particularly useful in larger applications where managing related classes can become complex. By understanding these concepts, you can write more maintainable and organized JavaScript code.