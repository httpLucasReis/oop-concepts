# OOP concepts 
__I created this repository to share the resumues of my OOP classes. I hope to help you! bye 👋👋👋__

# Oriented Objects Programming

## Pre-OOP

- The programmer can put related functions together in one file, but the grouping is just a convention and the compiler does not enforce it in a significant way.

## OOP

- In OOP, the logical arrangement of the code is changed. Instead of an informal arrangement of functions into different files, functionality is officially and tightly grouped with the type that it operates on.
- You can use easily libraries — Code Re-Use
- Modularity features
- The clueless Client Test = The language should encourage the right client behavior, discourage common client errors, and politely alert the client if there is an error

## Basic concepts

### Class

- A class is like a type in the classical language. Instead of just storing size and structural information for its data, a class also stores the operation which will apply to the data.
- Class = Storage + Behavior
- It creates a logical coupling between data and the operations on that data.
- Bundle the verbs with their nouns.
- Names of classes always start with capital characters

### Example of class in Javascript

```jsx
class Car {
	constructor(_factory, _model){
		this.factory = _factory
		this.model = _model
	}
}
```

- constructor is a type of subroutine called to create an object.
- It prepares the new object for use.

### Objects

- An object is a run-time value that stores state and belongs to some class.
- Objects know what class they belong to, and so they automatically know what operations they are capable of.
- The word "instance" is another word of "object"

### Example of how to create a object instance in Javascript

```jsx
class Car {
	constructor(_factory, _model) {
		this.factory = _factory
		this.model = _model
	}
}

// "New" show you will create an object.
const ford = new Car('Ford', 'Mustang')
```

## Massage and Method

- OOP uses "messages" instead of functions calls.
- Method ≠ Functions
- An object to perform an operation on itself.
- Object is like a Receiver.
- It knows what operations it can perform, because it knows it's class, and the class define all methods or operations for it's instances.

### Example of class in Javascript

```jsx
class Car {
	constructor(_factory, _model) {
		this.factory = _factory
		this.model = _model
	}

	turnOn() {
		return "Car is turning on... Turned on."
	}

	turnOff() {
		return "Car is turning off... turned off"
	}
}

// "New" show you will create an object.
const ford = new Car('Ford', 'Mustang')
```

## Message Send Syntax

- Almost all languages use the syntax: appending the message to the desired receiver with a dot.

### Example

```jsx
class Car {
	constructor(_factory, _model) {
		this.factory = _factory
		this.model = _model
	}

	turnOn() {
		return "Car is turning on... Turned on."
	}

	turnOff() { 
		return "Car is turning off... turned off"
	}
}

```

### C++, Java and Javascript syntax

```jsx
objectInstance.method();
```

### Python syntax

```python
objectInstance.method()
```

### PHP syntax

```php
$objectInstance->method();
```

## Important principles

### Encapsulation

- Refers to protecting the internals of an object from direct manipulation by the client.
- The client can send messages, but he can not change the bits in an object.
- The object's state is only touched by its own methods.

```jsx
// In any cases you need to use babel-presets.

class Car {
	factory;
	model;
	#year = 2021
	
	constructor(_factory, _model) {
		this.factory = _factory
		this.model = _model
	}

	get factory() {
		return this.factory
	}
	
	get model() {
		return this.model
	}

	get year() {
		return this.#year
	}

	turnOn() {
		return "Car is turning on... Turned on."
	}

	turnOff() {
		return "Car is turning off... turned off"
	}
}

```

- I will explain about public, private, and protected attributes another day. They also are really important concepts.
- (Read about Babel)[https://babeljs.io/]

## Inheritance

- Modularity and encapsulation are perhaps the most important concepts of OOP.

### Classes hierarchy

- Classes in OOP are arranged in a tree-like hierarchy.
- First we have a "superclass". It's the class above it in the tree.
- All the classes below are "subclasses"
- The hierarchy helps add logic to a collection of classes.

<img height="185" src="https://user-images.githubusercontent.com/62820717/107862421-86412f00-6e2b-11eb-8926-dae111cf604b.png">

### Example

### Using inheritance

- Is the process by which a class inherits the properties of its superclasses.
- Methods are inherited

<img height="200" src="https://user-images.githubusercontent.com/62820717/107862520-f9e33c00-6e2b-11eb-9a3e-962a8d695ebc.png">

```jsx
class  Player {
	constructor(_color, _age, _name){
		this.color = _color
		this.age = _age
		this.name = _name
	}
	
	walk() {
		return "I'm walking now"
	}

	run() { 
		return "I'm running now"
	}
}

class Knight extends Player {
	constructor(_color, _age, _name) {
		super(_color, _age, _name)
	}

	shout() {
		return "I'm shouting now, HAAAAAAAAAAAAAAAAAH"
	}
}

```

### Polymorphism

- Many classes in a program will respond to some common message.
- If you do not know which method was inherited, polymorphism help to rewrite this method.
- It is important when your code is complex enough that you are no longer sure of the exact class of an object.

```jsx
class  Player {
	constructor(_color, _age, _name){
		this.color = _color
		this.age = _age
		this.name = _name
	}
	
	walk() {
		return "I'm walking now"
	}

	run() { 
		return "I'm running now"
	}
}

class Knight extends Player {
	constructor(_color, _age, _name) {
		super(_color, _age, _name)
	}

	run () {
		return "I'm running more then everybody now"
	}

	shout() {
		return "I'm shouting now, HAAAAAAAAAAAAAAAAAH"
	}
}

```
