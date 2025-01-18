+++
date = '2025-01-04T18:39:08+08:00'
draft = false
title = 'Cs61b Notes'
+++

## Start
### Jan 4, 2025
At the beginning of 2025, now I start to learn UC Berkeley **CS 61B** , which I have been looking forward to for a long time.

I plan to keep a record on my progress.

---
## Week 1
### Lecture 1 - Introduction
>A great feature of 61B: Once you’re done: the confident sense that you can build any software.
>
>For most projects, the learning objective is NOT "can you write code in Java", but rather "**can you develop a solution to a problem from scratch**"

> Learning occurs by doing

For me, also try to appreciate the **beauty** of cs and mathematics in the process of learning :)
With joy!

---

**Hello World** - First Java program
``` java
pubulic class HelloWorld{
    public static void main(String[] args) {
        System.out.println("hello world");
    }
}

```
Reflections on Hello World：
- In Java, all code must be part of a **class**, which defined with public class CLASSNAME
- use { } to delineate the beginning and ending of things.
- end lines with a semicolon.
- inside public static void main(String[] args)

**Java is an object oriented language with strict requirements.**

---

**Hello Numbers**
```java
public class HelloNumbers {
   public static void main(String[] args) {

      int x = 0; /** Takeaway :) */
      while (x < 10) {
         System.out.println(x);
         x = x + 1;
      }

      x = "horse"; // program doesn't run
   }
}
```
Reflections on Hello Numbers: 
- **variables** need to be declared in advance; must have a specific type; Java variable types can never change; Types are verified before the code even runs

Java is **statically typed**!
- All variables, parameters, and methods must have a declared type, which never changes.
- The compiler checks that all the types in your program are compatible before the program ever runs
    - This is unlike a language like Python, where type checks are performed DURING execution.

---

**Lager**
```java
/** Demonstrates creation of a method in Java. */
public class LargerDemo {
   /** Returns the larger of x and y. */
   public static int larger(int x, int y) { /** Takeaway :) */
      if (x > y) {
         return x;
      }
      return y;
   }

   public static void main(String[] args) {
      System.out.println(larger(-5, 10));
   }
}
```
Reflections on Lager:
- So in Java, all functions are **methods**.
- All parameters of a function must have a declared type, and the return value of the function must have a declared type.
- Functions in Java return only one value!

---

**Compilation vs. Interpretation**
In Java, compilation and interpretation are two separate steps.

<img src="/static/images/cs61_notes_lec1_twosteps.jpg" style="width: 80%; height: auto; border: 5px solid rgba(255, 255, 255, 0.7); border-radius: 10px; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);">

- Good: get rid of **type errors**
- Bad: Verbose

```shell
$ javac HelloWorld.java
$ ls
HelloWorld.class  HelloWorld.java
$ java HelloWorld
Hello World!
```
---

**CS61A Review: Object-Oriented Programming**

- A model for organizing programs: modularity, data abstraction
- Objects and classes
```java
public class Car {
   public String model;   /** Takeaway :) */
   public int gas;

   public Car(String m) {
       model = m;
       gas = 5;
   }

   public void drive() {
       if (gas < 5) {
           System.out.println("Cannot drive!");
           return;
       }
       gas -= 5;
       System.out.println(model + " goes vroom!");
   }

   public int gasLeft() {
       return gas;   /** using self is not mandatory :) */
   }

   public void addGas(int amount) {
       gas = gas + amount;
   }
}
```
```java
public static void main(String[] args) {
   Car c1;  // Declare the variables of type Car before using them
   Car c2;  // The new keyword instantiates a new object

   c1 = new Car("Honda Civic");
   c2 = new Car("Model T");

   System.out.println(c1.gasLeft()); // Use dot notation to access methods of an object.

   c1.drive(); // Honda Civic goes vroom
   System.out.println(c1.gasLeft()); // 0

   c1.addGas(1);
   System.out.println(c1.gasLeft()); // 1

   c1.drive(); // Cannot drive

   System.out.println(c2.gasLeft()); // 5
}
```
---
#### Lab 01 - Setup
introduction to the terminal, git, Java, and IntelliJ:
- [x] [How to use the terminal](https://fa24.datastructur.es/labs/lab01/terminal/)
- [ ] [Using Git Guide](https://fa24.datastructur.es/resources/guides/git/)
- [X] setup

---
#### Homework 0A: Java Syntax
- [X] 4 small exersices 

---
### Lecture 2 - Defining and Using Classes



    

