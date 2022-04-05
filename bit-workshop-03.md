# BIT Workshop 03

## Agenda

- Code smells
- Code anti-patterns

### Code smells

#### Long method

**What is this code smell?** A method that contains too many lines of code. Here is an example:

```c#
void otherFunc() {}

void someFunc() {
  this.otherFunc();
  
  // Code doing something one
  
  // Code doing something two
  
  // Code doing something three
}
```

**How do you fix this?** Extract the code into separate methods. Here is an example:

```c#
void otherFunc() {}
void codeDoingSomethingOne() {}
void codeDoingSomethingTwo() {}
void codeDoingSomethingThree() {}

void someFunc() {
  this.otherFunc();
  this.codeDoingSomethingOne();
  this.codeDoingSomethingTwo();
  this.codeDoingSomethingThree();
}
```

**Question: What are the benefits?**

#### Large class

**What is this code smell?** A class that contains fields and methods. Here is an example:



**How do you fix this?** Extract the class into either a class, subclass or interface.

#### Long parameter list
#### Data clumps
#### Switch statement
#### Temp field

### Code anti-patterns
