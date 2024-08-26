# **Android development**

## **Java**

### 1. **Java Basics**
   - **[Variables and Data Types](#variables-and-data-types)**
   - **[Operators](#operators)**
   - **[Control Flow Statements](#control-flow-statements)**
   - **[Methods and Functions](#methods-and-functions)**
   - **[Arrays](#arrays)**

### 2. **Java Object-Oriented Concepts**
   - **[Classes and Objects](#classes-and-objects)**
   - **[Inheritance](#inheritance)**
   - **[Polymorphism](#polymorphism)**
   - **[Encapsulation](#encapsulation)**
   - **[Abstraction](#abstraction)**

### 3. **Multithreading and Exception Handling**
   - **[Creating and Managing Threads](#creating-and-managing-threads)**
   - **[Synchronization](#synchronization)**
   - **[Exceptions Handling](#exception-handling)**
   - **[Custom Exceptions](#custom-exceptions)**

### 4. **Generics and Collection Classes**
   - **[Generic Classes and Methods](#generic-classes-and-methods)**
   - **[Collection Classes](#collection-classes)**
   - **[Iterator Interface](#iterator-interface)**
   - **[Comparable and Comparator Interfaces](#comparable-and-comparator-interfaces)**

### 5. **Java Annotations**
   - **[Purpose of Annotations](#purpose-of-annotations)**
   - **[Built in Annotations](#built-in-annotations)** 
   - **[Meta Annotations](#meta-annotations)**
   - **[Custom Annotations](#custom-annotations)** 
   - **[Annotations in Java Frameworks](#annotations-in-java-frameworks)**

## XML:
### 1. **Basics of XML**
   - **What is XML?**
   - **Purpose of XML in Android development**

### 2. **Structure**
   - **Declaration (`<?xml version="1.0"?>`)**
   - **Root elements and nesting**
   - **Well-formed XML rules**

### 3. **Syntax**
   - **Tags, attributes, and values**
   - **Namespaces and schemas**

### 4. **Elements**
   - **Defining elements**
   - **Attributes vs. elements**
   - **Empty vs. non-empty elements**
   - **Hierarchical structure in XML**

---

### 1. <a name="java"></a>**Java Basics**

### <a name="variables-and-data-types"></a>**Variables and Data Types**
   - **Variables**: A variable in Java is a container that holds data. Each variable has a specific data type, which determines the size and type of the value it can store.
     - **Syntax**: `dataType variableName = value;`
     - **Example**: `int age = 25;`
   - **Data Types**: Java has two categories of data types:
     1. **Primitive Data Types**: These are the most basic data types that are built into the language.
        - **byte**: 8-bit integer, range: -128 to 127
        - **short**: 16-bit integer, range: -32,768 to 32,767
        - **int**: 32-bit integer, range: -2^31 to 2^31-1
        - **long**: 64-bit integer, range: -2^63 to 2^63-1
        - **float**: 32-bit floating-point, range: approximately ±3.40282347E+38F
        - **double**: 64-bit floating-point, range: approximately ±1.79769313486231570E+308
        - **char**: 16-bit Unicode character, range: 0 to 65,535
        - **boolean**: Represents true or false
     2. **Reference Data Types**: These refer to objects and arrays. They store the address of the value rather than the value itself.
        - **Example**: `String name = "John";`

### <a name="operators"></a>**Operators**
   - **Arithmetic Operators**: Used for performing basic mathematical operations.
     - `+` (Addition), `-` (Subtraction), `*` (Multiplication), `/` (Division), `%` (Modulus)
     - **Example**: `int sum = 10 + 5; // sum is 15`
   - **Relational Operators**: Used for comparing two values.
     - `==` (Equal to), `!=` (Not equal to), `>` (Greater than), `<` (Less than), `>=` (Greater than or equal to), `<=` (Less than or equal to)
     - **Example**: `boolean isEqual = (10 == 10); // true`
   - **Logical Operators**: Used for combining multiple boolean expressions.
     - `&&` (Logical AND), `||` (Logical OR), `!` (Logical NOT)
     - **Example**: `boolean result = (5 > 3) && (4 < 6); // true`
   - **Assignment Operators**: Used for assigning values to variables.
     - `=` (Assignment), `+=`, `-=`, `*=`, `/=`, `%=`
     - **Example**: `int x = 10; x += 5; // x is now 15`

### <a name="control-flow-statements"></a>**Control Flow Statements**
   - **If-Else Statement**: Used for making decisions in your code.
     - **Syntax**:
       ```java
       if (condition) {
           // code to be executed if condition is true
       } else {
           // code to be executed if condition is false
       }
       ```
     - **Example**:
       ```java
       int number = 10;
       if (number > 0) {
           System.out.println("Positive number");
       } else {
           System.out.println("Negative number");
       }
       ```
   - **Switch Statement**: An alternative to if-else for multiple conditions based on a single variable.
     - **Syntax**:
       ```java
       switch (variable) {
           case value1:
               // code to be executed
               break;
           case value2:
               // code to be executed
               break;
           default:
               // code to be executed if none of the cases match
       }
       ```
     - **Example**:
       ```java
       int day = 3;
       switch (day) {
           case 1:
               System.out.println("Monday");
               break;
           case 2:
               System.out.println("Tuesday");
               break;
           case 3:
               System.out.println("Wednesday");
               break;
           default:
               System.out.println("Other day");
       }
       ```
   - **Loops**: Used for executing a block of code multiple times.
     - **For Loop**: Ideal for iterating a specific number of times.
       - **Syntax**:
         ```java
         for (initialization; condition; update) {
             // code to be executed
         }
         ```
       - **Example**:
         ```java
         for (int i = 0; i < 5; i++) {
             System.out.println("Count: " + i);
         }
         ```
     - **While Loop**: Continues as long as a condition is true.
       - **Syntax**:
         ```java
         while (condition) {
             // code to be executed
         }
         ```
       - **Example**:
         ```java
         int i = 0;
         while (i < 5) {
             System.out.println("Count: " + i);
             i++;
         }
         ```
     - **Do-While Loop**: Similar to the while loop, but the condition is checked after the code has executed, ensuring it runs at least once.
       - **Syntax**:
         ```java
         do {
             // code to be executed
         } while (condition);
         ```
       - **Example**:
         ```java
         int i = 0;
         do {
             System.out.println("Count: " + i);
             i++;
         } while (i < 5);
         ```

### <a name="methods-and-functions"></a>**Methods and Functions**
   - **Methods**: Blocks of code that perform a specific task and can be reused throughout your code. Methods can return values or be `void` (returning nothing).
     - **Syntax**:
       ```java
       returnType methodName(parameters) {
           // code to be executed
           return value; // if returnType is not void
       }
       ```
     - **Example**:
       ```java
       public int add(int a, int b) {
           return a + b;
       }
       public void printMessage(String message) {
           System.out.println(message);
       }
       ```
     - **Calling Methods**:
       ```java
       int sum = add(5, 10); // sum is 15
       printMessage("Hello, World!"); // prints "Hello, World!"
       ```

### <a name="arrays"></a>**Arrays**
   - **Arrays**: A collection of elements of the same type, stored in contiguous memory locations.
     - **Syntax**:
       ```java
       dataType[] arrayName = new dataType[size];
       ```
     - **Example**:
       ```java
       int[] numbers = new int[5]; // creates an array of integers with 5 elements
       int[] numbers = {1, 2, 3, 4, 5}; // creates an array and initializes it with values
       ```
     - **Accessing Elements**:
       ```java
       int firstNumber = numbers[0]; // gets the first element (1)
       numbers[2] = 10; // sets the third element to 10
       ```
     - **Iterating Over Arrays**:
       ```java
       for (int i = 0; i < numbers.length; i++) {
           System.out.println(numbers[i]);
       }
       ```

---

### 2. **Java Object-Oriented Concepts**

### <a name="classes-and-objects"></a>**Classes and Objects**
   - **Class**: A blueprint for creating objects. It defines the properties (fields) and behaviors (methods) that the objects created from it will have.
     - **Syntax**:
       ```java
       class ClassName {
           // fields (variables)
           // methods (functions)
       }
       ```
     - **Example**:
       ```java
       class Car {
           String brand;
           int speed;

           void accelerate() {
               speed += 10;
           }
       }
       ```
   - **Object**: An instance of a class. Objects are created from classes using the `new` keyword.
     - **Syntax**:
       ```java
       ClassName objectName = new ClassName();
       ```
     - **Example**:
       ```java
       Car myCar = new Car(); // creates a new Car object
       myCar.brand = "Toyota";
       myCar.accelerate();
       ```

### <a name="inheritance"></a>**Inheritance**
   - **Inheritance**: A mechanism that allows one class (child or subclass) to inherit fields and methods from another class (parent or superclass). This promotes code reusability.
     - **Syntax**:
       ```java
       class ChildClass extends ParentClass {
           // additional fields and methods
       }
       ```
     - **Example**:
       ```java
       class Vehicle {
           int speed;
           void move() {
               System.out.println("Vehicle is moving");
           }
       }

       class Car extends Vehicle {
           int numberOfDoors;
       }

       Car myCar = new Car();
       myCar.move(); // Inherited method from Vehicle class
       ```
   - **Types of Inheritance**:
     - **Single Inheritance**: A class inherits from one superclass.
     - **Multilevel Inheritance**: A class inherits from a subclass, forming a chain.
     - **Hierarchical Inheritance**: Multiple classes inherit from a single superclass.
     - **Note**: Java does not support multiple inheritance (a class cannot inherit from more than one class directly) to avoid complexity and ambiguity. Instead, it uses interfaces for this purpose.

### <a name="polymorphism"></a>**Polymorphism**
   - **Polymorphism**: The ability of an object to take on many forms. It allows one interface to be used for a general class of actions.
     - **Types of Polymorphism**:
       1. **Compile-Time Polymorphism (Method Overloading)**:
          - The ability to define multiple methods with the same name but different parameters (different types, number of parameters, or both).
          - **Example**:
            ```java
            class Calculator {
                int add(int a, int b) {
                    return a + b;
                }

                double add(double a, double b) {
                    return a + b;
                }
            }

            Calculator calc = new Calculator();
            int sum1 = calc.add(5, 10);        // Calls the first add method
            double sum2 = calc.add(5.5, 10.5); // Calls the second add method
            ```
       2. **Run-Time Polymorphism (Method Overriding)**:
          - The ability of a subclass to provide a specific implementation of a method that is already defined in its superclass.
          - **Example**:
            ```java
            class Animal {
                void sound() {
                    System.out.println("Animal makes a sound");
                }
            }

            class Dog extends Animal {
                @Override
                void sound() {
                    System.out.println("Dog barks");
                }
            }

            Animal myDog = new Dog();
            myDog.sound(); // Outputs: Dog barks (calls the overridden method in Dog class)
            ```

### <a name="encapsulation"></a>**Encapsulation**
   - **Encapsulation**: The process of wrapping the data (variables) and code (methods) into a single unit, known as a class. It also involves restricting direct access to some of the object's components, which is achieved using access modifiers.
     - **Access Modifiers**:
       - **private**: Accessible only within the same class.
       - **protected**: Accessible within the same package and subclasses.
       - **public**: Accessible from any other class.
       - **default** (no modifier): Accessible within the same package.
     - **Getters and Setters**: Methods that provide controlled access to private fields.
       - **Example**:
         ```java
         class Employee {
             private String name;
             private double salary;

             // Getter for name
             public String getName() {
                 return name;
             }

             // Setter for name
             public void setName(String name) {
                 this.name = name;
             }

             // Getter for salary
             public double getSalary() {
                 return salary;
             }

             // Setter for salary
             public void setSalary(double salary) {
                 this.salary = salary;
             }
         }

         Employee emp = new Employee();
         emp.setName("John Doe");
         emp.setSalary(50000.0);
         System.out.println(emp.getName() + " earns " + emp.getSalary());
         ```

### <a name="abstraction"></a>**Abstraction**
   - **Abstraction**: The concept of hiding the complex implementation details and showing only the essential features of the object. In Java, abstraction is achieved using abstract classes and interfaces.
     - **Abstract Class**: A class that cannot be instantiated on its own and can have both abstract methods (without a body) and concrete methods (with a body).
       - **Syntax**:
         ```java
         abstract class AbstractClassName {
             // abstract method (no body)
             abstract void abstractMethod();

             // regular method (with body)
             void regularMethod() {
                 // implementation
             }
         }
         ```
       - **Example**:
         ```java
         abstract class Animal {
             abstract void sound();

             void eat() {
                 System.out.println("Animal is eating");
             }
         }

         class Dog extends Animal {
             @Override
             void sound() {
                 System.out.println("Dog barks");
             }
         }

         Animal myDog = new Dog();
         myDog.sound(); // Outputs: Dog barks
         myDog.eat();   // Outputs: Animal is eating
         ```
     - **Interface**: A completely abstract class that contains only abstract methods. Classes that implement an interface must provide an implementation for all of its methods.
       - **Syntax**:
         ```java
         interface InterfaceName {
             void method1();
             void method2();
         }
         ```
       - **Example**:
         ```java
         interface Animal {
             void sound();
             void sleep();
         }

         class Dog implements Animal {
             @Override
             public void sound() {
                 System.out.println("Dog barks");
             }

             @Override
             public void sleep() {
                 System.out.println("Dog sleeps");
             }
         }

         Dog myDog = new Dog();
         myDog.sound(); // Outputs: Dog barks
         myDog.sleep(); // Outputs: Dog sleeps
         ```

---

### 3. **Multithreading and Exception Handling**

**Multithreading** is a feature in Java that allows multiple threads to run concurrently. It is crucial in developing applications that perform several tasks simultaneously, leading to better resource utilization and enhanced application performance.

### <a name="creating-and-managing-threads"></a>**Creating and Managing Threads**:
   - **Thread Creation**: A thread is the smallest unit of a process that can run concurrently with other threads. In Java, there are two primary ways to create a thread:
     - **By Extending the `Thread` Class**:
       - You can create a new thread by creating a subclass of `Thread` and overriding the `run()` method.
       - Example:
         ```java
         class MyThread extends Thread {
             public void run() {
                 System.out.println("Thread is running");
             }
         }

         public class Main {
             public static void main(String[] args) {
                 MyThread thread = new MyThread();
                 thread.start(); // Start the thread
             }
         }
         ```
     - **By Implementing the `Runnable` Interface**:
       - You can also create a thread by implementing the `Runnable` interface and passing an instance of your class to a `Thread` object.
       - Example:
         ```java
         class MyRunnable implements Runnable {
             public void run() {
                 System.out.println("Runnable is running");
             }
         }

         public class Main {
             public static void main(String[] args) {
                 MyRunnable runnable = new MyRunnable();
                 Thread thread = new Thread(runnable);
                 thread.start(); // Start the thread
             }
         }
         ```

### <a name="synchronization"></a>**Synchronization**:
   - **Purpose**: Synchronization is used to control the access of multiple threads to shared resources, preventing data inconsistency and ensuring thread safety.
   - **Synchronized Blocks and Methods**:
     - A block of code can be synchronized using the `synchronized` keyword to ensure that only one thread can execute it at a time.
     - Example:
       ```java
       class Counter {
           private int count = 0;

           public synchronized void increment() {
               count++;
           }

           public int getCount() {
               return count;
           }
       }

       public class Main {
           public static void main(String[] args) throws InterruptedException {
               Counter counter = new Counter();

               Thread t1 = new Thread(() -> {
                   for (int i = 0; i < 1000; i++) {
                       counter.increment();
                   }
               });

               Thread t2 = new Thread(() -> {
                   for (int i = 0; i < 1000; i++) {
                       counter.increment();
                   }
               });

               t1.start();
               t2.start();

               t1.join();
               t2.join();

               System.out.println(counter.getCount()); // Expected output: 2000
           }
       }
       ```

1. **Thread Methods**:
   - **start()**: Begins the execution of the thread by calling its `run()` method.
   - **run()**: The method that contains the code to be executed by the thread.
   - **sleep(long millis)**: Pauses the execution of the thread for the specified duration.
   - **join()**: Waits for the thread to finish its execution.
   - **yield()**: Suggests that the current thread allows other threads to execute.
   - **interrupt()**: Interrupts a thread that is in a waiting or sleeping state.

2. **Deadlock**:
   - **Deadlock** occurs when two or more threads are waiting for each other to release resources, causing them to be stuck indefinitely.
   - Example:
     ```java
     class A {
         synchronized void methodA(B b) {
             System.out.println("Thread1 starts execution of methodA()");
             try { Thread.sleep(100); } catch (InterruptedException e) {}
             b.last();
         }

         synchronized void last() {
             System.out.println("Inside A.last()");
         }
     }

     class B {
         synchronized void methodB(A a) {
             System.out.println("Thread2 starts execution of methodB()");
             try { Thread.sleep(100); } catch (InterruptedException e) {}
             a.last();
         }

         synchronized void last() {
             System.out.println("Inside B.last()");
         }
     }

     public class DeadlockExample implements Runnable {
         A a = new A();
         B b = new B();

         DeadlockExample() {
             Thread t = new Thread(this);
             t.start();
             a.methodA(b); // main thread
         }

         public void run() {
             b.methodB(a); // other thread
         }

         public static void main(String[] args) {
             new DeadlockExample();
         }
     }
     ```

### <a name="exception-handling"></a>**Exception Handling**

**Exception Handling** is a mechanism in Java to handle runtime errors, allowing the program to continue execution without terminating unexpectedly.

1. **Types of Exceptions**:
   - **Checked Exceptions**: Checked at compile-time, e.g., `IOException`.
   - **Unchecked Exceptions**: Occur at runtime, e.g., `NullPointerException`.
   - **Errors**: Serious issues that a program should not handle, e.g., `OutOfMemoryError`.

2. **Handling Exceptions with try-catch blocks**:
   - **try-catch block**: Used to catch exceptions and handle them.
   - Example:
     ```java
     public class Main {
         public static void main(String[] args) {
             try {
                 int data = 50 / 0; // This will throw an ArithmeticException
             } catch (ArithmeticException e) {
                 System.out.println("Cannot divide by zero: " + e.getMessage());
             } finally {
                 System.out.println("This block is always executed");
             }
         }
     }
     ```

### <a name="custom-exceptions"></a>**Custom Exceptions**:
   - You can create your own exceptions by extending the `Exception` class.
   - Example:
     ```java
     class MyException extends Exception {
         MyException(String message) {
             super(message);
         }
     }

     public class Main {
         public static void main(String[] args) {
             try {
                 throw new MyException("Custom Exception");
             } catch (MyException e) {
                 System.out.println("Caught: " + e.getMessage());
             }
         }
     }
     ```

3. **Throws Clause**:
   - The `throws` keyword is used in method signatures to indicate that a method might throw an exception.
   - Example:
     ```java
     public class Main {
         static void checkAge(int age) throws AgeException {
             if (age < 18) {
                 throw new AgeException("Age is not valid");
             } else {
                 System.out.println("Valid age");
             }
         }

         public static void main(String[] args) {
             try {
                 checkAge(16);
             } catch (AgeException e) {
                 System.out.println("Caught: " + e.getMessage());
             }
         }
     }

     class AgeException extends Exception {
         AgeException(String message) {
             super(message);
         }
     }
     ```

4. **Finally Block**:
   - A `finally` block is always executed after the try-catch block, regardless of whether an exception was thrown or not.
   - It is commonly used to release resources like file streams, database connections, etc.
   - Example:
     ```java
     public class Main {
         public static void main(String[] args) {
             try {
                 int data = 50 / 0;
             } catch (ArithmeticException e) {
                 System.out.println(e);
             } finally {
                 System.out.println("Finally block is executed");
             }
         }
     }
     ```

--- 

### Generics in Java

**Generics** in Java are a powerful feature that allows you to create classes, interfaces, and methods with type parameters. This enables code reusability, type safety, and flexibility without the need to write duplicate code for different data types.

#### Key Concepts of Generics

1. **Why Use Generics?**
   - **Type Safety**: Generics ensure that the code is type-safe at compile time, preventing `ClassCastException` at runtime.
   - **Code Reusability**: You can write generic algorithms that work with any type of data, making your code more reusable and easier to maintain.
   - **Elimination of Casts**: Generics eliminate the need for explicit type casting, making the code cleaner and reducing errors.

2. **Generic Classes**
   - A generic class is a class with one or more type parameters. These parameters are specified within angle brackets `< >` after the class name.
   - **Syntax**:
     ```java
     class Box<T> {
         private T value;

         public void setValue(T value) {
             this.value = value;
         }

         public T getValue() {
             return value;
         }
     }
     ```
   - **Example**:
     ```java
     public class Main {
         public static void main(String[] args) {
             Box<Integer> integerBox = new Box<>();
             integerBox.setValue(10);
             System.out.println("Integer Value: " + integerBox.getValue());

             Box<String> stringBox = new Box<>();
             stringBox.setValue("Hello Generics");
             System.out.println("String Value: " + stringBox.getValue());
         }
     }
     ```
   - Here, `T` is a type parameter that can be replaced with any type, such as `Integer` or `String`.

3. **Generic Methods**
   - A generic method is a method that has its own type parameter(s), independent of any class-level type parameters.
   - **Syntax**:
     ```java
     public <T> void printArray(T[] array) {
         for (T element : array) {
             System.out.println(element);
         }
     }
     ```
   - **Example**:
     ```java
     public class Main {
         public static <T> void printArray(T[] array) {
             for (T element : array) {
                 System.out.println(element);
             }
         }

         public static void main(String[] args) {
             Integer[] intArray = {1, 2, 3, 4};
             String[] stringArray = {"Hello", "Generics"};

             printArray(intArray);  // Output: 1 2 3 4
             printArray(stringArray);  // Output: Hello Generics
         }
     }
     ```
   - The `<T>` before the return type specifies that this method is generic, and `T` can be any data type.

4. **Bounded Type Parameters**
   - You can restrict the types that can be used as arguments for a type parameter using bounds.
   - **Upper Bound**: Specifies that the type parameter must be a subclass of a particular class.
   - **Syntax**:
     ```java
     class Box<T extends Number> {
         private T value;

         public void setValue(T value) {
             this.value = value;
         }

         public T getValue() {
             return value;
         }
     }
     ```
   - **Example**:
     ```java
     public class Main {
         public static void main(String[] args) {
             Box<Integer> intBox = new Box<>();
             intBox.setValue(10);
             System.out.println("Integer Value: " + intBox.getValue());

             Box<Double> doubleBox = new Box<>();
             doubleBox.setValue(10.5);
             System.out.println("Double Value: " + doubleBox.getValue());

             // Box<String> stringBox = new Box<>(); // Error: String is not a subclass of Number
         }
     }
     ```
   - Here, `T extends Number` means that the type parameter `T` can only be a `Number` or its subclasses (e.g., `Integer`, `Double`).

5. **Wildcards in Generics**
   - Wildcards are special placeholders used in generics to represent unknown types.
   - **Types of Wildcards**:
     - **Unbounded Wildcard (`?`)**: Represents an unknown type. It can be any type.
       ```java
       public void printList(List<?> list) {
           for (Object element : list) {
               System.out.println(element);
           }
       }
       ```
     - **Upper Bounded Wildcard (`? extends T`)**: Represents an unknown type that is a subtype of `T`.
       ```java
       public void printNumbers(List<? extends Number> list) {
           for (Number number : list) {
               System.out.println(number);
           }
       }
       ```
     - **Lower Bounded Wildcard (`? super T`)**: Represents an unknown type that is a supertype of `T`.
       ```java
       public void addNumbers(List<? super Integer> list) {
           list.add(10);
           list.add(20);
       }
       ```
   - **Example**:
     ```java
     public class Main {
         public static void printNumbers(List<? extends Number> list) {
             for (Number number : list) {
                 System.out.println(number);
             }
         }

         public static void main(String[] args) {
             List<Integer> intList = Arrays.asList(1, 2, 3);
             List<Double> doubleList = Arrays.asList(1.1, 2.2, 3.3);

             printNumbers(intList);  // Output: 1 2 3
             printNumbers(doubleList);  // Output: 1.1 2.2 3.3
         }
     }
     ```

6. **Generic Interfaces**
   - Like classes, interfaces can also be generic.
   - **Syntax**:
     ```java
     interface Pair<K, V> {
         K getKey();
         V getValue();
     }
     ```
   - **Example**:
     ```java
     class OrderedPair<K, V> implements Pair<K, V> {
         private K key;
         private V value;

         public OrderedPair(K key, V value) {
             this.key = key;
             this.value = value;
         }

         public K getKey() {
             return key;
         }

         public V getValue() {
             return value;
         }
     }

     public class Main {
         public static void main(String[] args) {
             Pair<String, Integer> pair = new OrderedPair<>("One", 1);
             System.out.println("Key: " + pair.getKey() + ", Value: " + pair.getValue());
         }
     }
     ```

---

### Collection Classes in Java

**Collections** in Java are data structures that are used to store, retrieve, and manipulate groups of objects. Java provides a rich set of collection classes in the `java.util` package, forming part of the Java Collections Framework (JCF).

#### Key Concepts of Collections

1. **Collection Framework Overview**
   - The Collection Framework provides a unified architecture for manipulating and representing collections.
   - **Interfaces**: Define the abstract data types (e.g., `List`, `Set`, `Map`).
   - **Implementations**: Concrete classes that implement these interfaces (e.g., `ArrayList`, `HashSet`, `HashMap`).

2. **List Interface**
   - A `List` is an ordered collection (also known as a sequence) that allows duplicates.
   - **Common Implementations**:
     - **ArrayList**: Resizable array implementation.
       ```java
       List<String> list = new ArrayList<>();
       list.add("Apple");
       list.add("Banana");
       list.add("Orange");
       ```
     - **LinkedList**: Doubly-linked list implementation.
       ```java
       List<String> list = new LinkedList<>();
       list.add("Dog");
       list.add("Cat");
       list.add("Cow");
       ```
     - **Vector**: Synchronized resizable array implementation.
       ```java
       List<String> list = new Vector<>();
       list.add("Red");
       list.add("Green");
       list.add("Blue");
       ```

3. **Set Interface**
   - A `Set` is an unordered collection that does not allow duplicates.
   - **Common Implementations**:
     - **HashSet**: Uses a hash table for storage. No guarantee of order.
       ```java
       Set<String> set = new HashSet<>();
       set.add("One");
       set.add("Two");
       set.add("Three");
       ```
     - **LinkedHashSet**: Maintains insertion order.
       ```java
       Set<String> set = new LinkedHashSet<>();
       set.add("A");
       set.add("B");
       set.add("C");
       ```
     - **TreeSet**: Stores elements in a sorted (ascending) order.
       ```java
       Set<String> set = new TreeSet<>();
       set.add("X");
       set.add("Y");
       set.add("Z");
       ```

4. **Map Interface**
   - A `Map` is a collection of key-value pairs. Each key is unique, but values can be duplicated.
   - **Common Implementations**:
     - **HashMap**: Uses a hash table for storage. No guarantee of order.
       ```java
       Map<String, Integer> map = new HashMap<>();
       map.put("Apple", 10);
       map.put("Banana", 20);
       map.put("Orange", 30);
       ```
     - **LinkedHashMap

**: Maintains insertion order.
       ```java
       Map<String, Integer> map = new LinkedHashMap<>();
       map.put("Dog", 5);
       map.put("Cat", 10);
       map.put("Cow", 15);
       ```
     - **TreeMap**: Stores elements in a sorted (ascending) order based on keys.
       ```java
       Map<String, Integer> map = new TreeMap<>();
       map.put("One", 1);
       map.put("Two", 2);
       map.put("Three", 3);
       ```

5. **Queue Interface**
   - A `Queue` is a collection designed for holding elements prior to processing. It typically orders elements in a FIFO (First-In-First-Out) manner.
   - **Common Implementations**:
     - **LinkedList**: Can be used as a queue.
       ```java
       Queue<String> queue = new LinkedList<>();
       queue.add("One");
       queue.add("Two");
       queue.add("Three");
       ```
     - **PriorityQueue**: Orders elements according to their natural ordering or by a comparator provided at queue construction time.
       ```java
       Queue<Integer> queue = new PriorityQueue<>();
       queue.add(10);
       queue.add(5);
       queue.add(20);
       ```

6. **Iterator Interface**
   - An `Iterator` is an object that enables you to traverse a collection, obtain or remove elements.
   - **Example**:
     ```java
     List<String> list = new ArrayList<>();
     list.add("Apple");
     list.add("Banana");
     list.add("Orange");

     Iterator<String> iterator = list.iterator();
     while (iterator.hasNext()) {
         System.out.println(iterator.next());
     }
     ```

---

### 4. **Generics and Collection Classes**

###  <a name="generic-classes-and-methods"></a>**Generic Classes and Methods**  

Generics in Java are a powerful feature that allows you to create classes, interfaces, and methods with type parameters. This enables code reusability, type safety, and flexibility without the need to write duplicate code for different data types.

#### Key Concepts of Generics

1. **Why Use Generics?**
   - **Type Safety**: Ensures that the code is type-safe at compile time, preventing `ClassCastException` at runtime.
   - **Code Reusability**: Write generic algorithms that work with any type of data, making your code more reusable and easier to maintain.
   - **Elimination of Casts**: Removes the need for explicit type casting, making the code cleaner and reducing errors.

2. **Generic Classes**
   - A generic class is a class with one or more type parameters. These parameters are specified within angle brackets `< >` after the class name.
   - **Syntax**:
     ```java
     class Box<T> {
         private T value;

         public void setValue(T value) {
             this.value = value;
         }

         public T getValue() {
             return value;
         }
     }
     ```
   - **Example**:
     ```java
     public class Main {
         public static void main(String[] args) {
             Box<Integer> integerBox = new Box<>();
             integerBox.setValue(10);
             System.out.println("Integer Value: " + integerBox.getValue());

             Box<String> stringBox = new Box<>();
             stringBox.setValue("Hello Generics");
             System.out.println("String Value: " + stringBox.getValue());
         }
     }
     ```

3. **Generic Methods**
   - A generic method is a method that has its own type parameter(s), independent of any class-level type parameters.
   - **Syntax**:
     ```java
     public <T> void printArray(T[] array) {
         for (T element : array) {
             System.out.println(element);
         }
     }
     ```
   - **Example**:
     ```java
     public class Main {
         public static <T> void printArray(T[] array) {
             for (T element : array) {
                 System.out.println(element);
             }
         }

         public static void main(String[] args) {
             Integer[] intArray = {1, 2, 3, 4};
             String[] stringArray = {"Hello", "Generics"};

             printArray(intArray);  // Output: 1 2 3 4
             printArray(stringArray);  // Output: Hello Generics
         }
     }
     ```

4. **Bounded Type Parameters**
   - You can restrict the types that can be used as arguments for a type parameter using bounds.
   - **Upper Bound**: Specifies that the type parameter must be a subclass of a particular class.
   - **Syntax**:
     ```java
     class Box<T extends Number> {
         private T value;

         public void setValue(T value) {
             this.value = value;
         }

         public T getValue() {
             return value;
         }
     }
     ```
   - **Example**:
     ```java
     public class Main {
         public static void main(String[] args) {
             Box<Integer> intBox = new Box<>();
             intBox.setValue(10);
             System.out.println("Integer Value: " + intBox.getValue());

             Box<Double> doubleBox = new Box<>();
             doubleBox.setValue(10.5);
             System.out.println("Double Value: " + doubleBox.getValue());

             // Box<String> stringBox = new Box<>(); // Error: String is not a subclass of Number
         }
     }
     ```

5. **Wildcards in Generics**
   - Wildcards are special placeholders used in generics to represent unknown types.
   - **Types of Wildcards**:
     - **Unbounded Wildcard (`?`)**: Represents an unknown type.
       ```java
       public void printList(List<?> list) {
           for (Object element : list) {
               System.out.println(element);
           }
       }
       ```
     - **Upper Bounded Wildcard (`? extends T`)**: Represents an unknown type that is a subtype of `T`.
       ```java
       public void printNumbers(List<? extends Number> list) {
           for (Number number : list) {
               System.out.println(number);
           }
       }
       ```
     - **Lower Bounded Wildcard (`? super T`)**: Represents an unknown type that is a supertype of `T`.
       ```java
       public void addNumbers(List<? super Integer> list) {
           list.add(10);
           list.add(20);
       }
       ```
   - **Example**:
     ```java
     public class Main {
         public static void printNumbers(List<? extends Number> list) {
             for (Number number : list) {
                 System.out.println(number);
             }
         }

         public static void main(String[] args) {
             List<Integer> intList = Arrays.asList(1, 2, 3);
             List<Double> doubleList = Arrays.asList(1.1, 2.2, 3.3);

             printNumbers(intList);  // Output: 1 2 3
             printNumbers(doubleList);  // Output: 1.1 2.2 3.3
         }
     }
     ```

6. **Generic Interfaces**
   - Like classes, interfaces can also be generic.
   - **Syntax**:
     ```java
     interface Pair<K, V> {
         K getKey();
         V getValue();
     }
     ```
   - **Example**:
     ```java
     class OrderedPair<K, V> implements Pair<K, V> {
         private K key;
         private V value;

         public OrderedPair(K key, V value) {
             this.key = key;
             this.value = value;
         }

         public K getKey() {
             return key;
         }

         public V getValue() {
             return value;
         }
     }

     public class Main {
         public static void main(String[] args) {
             Pair<String, Integer> pair = new OrderedPair<>("One", 1);
             System.out.println("Key: " + pair.getKey() + ", Value: " + pair.getValue());
         }
     }
     ```

### <a name="collection-classes"></a>**Collection Classes**

Collections in Java are data structures used to store, retrieve, and manipulate groups of objects. Java provides a rich set of collection classes in the `java.util` package, forming part of the Java Collections Framework (JCF).

#### Key Concepts of Collections

1. **Collection Framework Overview**
   - The Collection Framework provides a unified architecture for manipulating and representing collections.
   - **Interfaces**: Define the abstract data types (e.g., `List`, `Set`, `Map`).
   - **Implementations**: Concrete classes that implement these interfaces (e.g., `ArrayList`, `HashSet`, `HashMap`).

2. **List Interface**
   - A `List` is an ordered collection (also known as a sequence) that allows duplicates.
   - **Common Implementations**:
     - **ArrayList**: Resizable array implementation.
       ```java
       List<String> list = new ArrayList<>();
       list.add("Apple");
       list.add("Banana");
       list.add("Orange");
       ```
     - **LinkedList**: Doubly-linked list implementation.
       ```java
       List<String> list = new LinkedList<>();
       list.add("Dog");
       list.add("Cat");
       list.add("Cow");
       ```
     - **Vector**: Synchronized resizable array implementation.
       ```java
       List<String> list = new Vector<>();
       list.add("Red");
       list.add("Green");
       list.add("Blue");
       ```

3. **Set Interface**
   - A `Set` is an unordered collection that does not allow duplicates.
   - **Common Implementations**:
     - **HashSet**: Uses a hash table for storage. No guarantee of order.
       ```java
       Set<String> set = new HashSet<>();
       set.add("One");
       set.add("Two");
       set.add("Three");
       ```
     - **LinkedHashSet**: Maintains insertion order.
       ```java
       Set<String> set = new LinkedHashSet<>();
       set.add("A");
       set.add("B");
       set.add("C");
       ```
     - **TreeSet**: Stores elements in a sorted (ascending) order.
       ```java
       Set<String> set = new TreeSet<>();
       set.add("X");
       set.add("Y");
       set.add("Z");
       ```

4. **Map Interface**
   - A `Map` is a collection of key-value pairs. Each key is unique, but values can be duplicated.
   - **Common Implementations**:
     - **HashMap**: Uses a hash table for storage. No guarantee of order.
       ```java
       Map<String, Integer> map = new HashMap<>();
       map.put("Apple", 10);
       map.put("Banana", 20);
       map.put("Orange", 30);
       ```
     - **LinkedHashMap**: Maintains insertion order.
       ```java
       Map<String, Integer> map = new

 LinkedHashMap<>();
       map.put("Monday", 1);
       map.put("Tuesday", 2);
       map.put("Wednesday", 3);
       ```
     - **TreeMap**: Stores elements in a sorted (ascending) order by key.
       ```java
       Map<String, Integer> map = new TreeMap<>();
       map.put("Red", 1);
       map.put("Green", 2);
       map.put("Blue", 3);
       ```

5. **Queue Interface**
   - A `Queue` is a collection designed for holding elements prior to processing. Typically, it follows a first-in, first-out (FIFO) order.
   - **Common Implementations**:
     - **PriorityQueue**: Stores elements with natural ordering or by a comparator.
       ```java
       Queue<Integer> queue = new PriorityQueue<>();
       queue.add(10);
       queue.add(20);
       queue.add(15);
       ```
     - **ArrayDeque**: Resizable-array implementation of the `Deque` interface.
       ```java
       Queue<String> queue = new ArrayDeque<>();
       queue.add("Alpha");
       queue.add("Beta");
       queue.add("Gamma");
       ```

### <a name="iterator-interface"></a>**Iterator Interface**

The `Iterator` interface provides methods to iterate over any Collection type. It offers a way to access elements sequentially without exposing the underlying structure.

#### Key Methods of Iterator

1. **hasNext()**: Returns `true` if the iteration has more elements.
2. **next()**: Returns the next element in the iteration.
3. **remove()**: Removes the last element returned by the iterator from the underlying collection.

#### Example:

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("Java");
        list.add("Python");
        list.add("C++");

        Iterator<String> iterator = list.iterator();
        while (iterator.hasNext()) {
            String value = iterator.next();
            System.out.println(value);
        }
    }
}
```

### <a name="comparable-and-comparator-interfaces"></a>**Comparable and Comparator Interfaces**

The `Comparable` and `Comparator` interfaces are used to define the natural ordering or custom ordering of objects in Java.

#### Comparable Interface

- The `Comparable` interface is used to impose a natural ordering on the objects of a class. A class that implements `Comparable` must override the `compareTo()` method.

- **Syntax**:
  ```java
  class Student implements Comparable<Student> {
      private String name;
      private int marks;

      public Student(String name, int marks) {
          this.name = name;
          this.marks = marks;
      }

      @Override
      public int compareTo(Student other) {
          return this.marks - other.marks;
      }
  }
  ```

- **Example**:
  ```java
  import java.util.*;

  public class Main {
      public static void main(String[] args) {
          List<Student> students = new ArrayList<>();
          students.add(new Student("Alice", 85));
          students.add(new Student("Bob", 75));
          students.add(new Student("Charlie", 90));

          Collections.sort(students);  // Sorts based on marks
          for (Student s : students) {
              System.out.println(s.getName() + ": " + s.getMarks());
          }
      }
  }
  ```

#### Comparator Interface

- The `Comparator` interface is used to define multiple ways of ordering objects. It is a functional interface that contains the `compare()` method.

- **Syntax**:
  ```java
  class StudentComparator implements Comparator<Student> {
      @Override
      public int compare(Student s1, Student s2) {
          return s1.getName().compareTo(s2.getName());
      }
  }
  ```

- **Example**:
  ```java
  import java.util.*;

  public class Main {
      public static void main(String[] args) {
          List<Student> students = new ArrayList<>();
          students.add(new Student("Alice", 85));
          students.add(new Student("Bob", 75));
          students.add(new Student("Charlie", 90));

          Collections.sort(students, new StudentComparator());  // Sorts based on name
          for (Student s : students) {
              System.out.println(s.getName() + ": " + s.getMarks());
          }
      }
  }
  ```

---


### 5. **Java Annotations**

**Java Annotations** are a powerful feature in Java that allows developers to add metadata to their code. This metadata can be used by the compiler, tools, or at runtime to influence the behavior of the program without directly affecting the code's execution. Annotations enhance code readability, maintainability, and the ability to automate tasks such as configuration and testing.


### <a name="purpose-of-annotations"></a>**Purpose of Annotations** 
   - **Information for the Compiler**: Annotations like `@Override` help the compiler enforce rules, such as ensuring that a method correctly overrides a method in a superclass.
   - **Code Analysis by Tools**: Tools and frameworks can use annotations to generate code, documentation, or configure components. For example, annotations in Spring or Hibernate can define behaviors without explicit code.
   - **Runtime Instructions**: Some annotations are retained at runtime and can be accessed using reflection, allowing dynamic processing based on the annotation data.

### <a name="built-in-annotations"></a>**Built in Annotations** 
   - **@Override**: Ensures a method is overriding a method in a superclass. If the method signature doesn't match, the compiler generates an error.
     ```java
     @Override
     void display() {
         System.out.println("Overridden method");
     }
     ```

   - **@Deprecated**: Marks a method or class as deprecated, signaling that it should no longer be used. The compiler issues warnings when the deprecated element is used.
     ```java
     @Deprecated
     void oldMethod() {
         System.out.println("This method is deprecated.");
     }
     ```

   - **@SuppressWarnings**: Tells the compiler to ignore specific warnings, such as unchecked operations or deprecation warnings.
     ```java
     @SuppressWarnings("unchecked")
     void addElements(List list) {
         list.add("Element");
     }
     ```

   - **@FunctionalInterface**: Ensures an interface is intended to be a functional interface, meaning it has exactly one abstract method.
     ```java
     @FunctionalInterface
     interface MyFunctionalInterface {
         void execute();
     }
     ```

   - **@SafeVarargs**: Suppresses warnings for possible heap pollution when using varargs.
     ```java
     @SafeVarargs
     final void printList(List<String>... lists) {
         for (List<String> list : lists) {
             System.out.println(list);
         }
     }
     ```

### <a name="meta-annotations"></a>**Meta Annotations** 
   - Meta-annotations are annotations that apply to other annotations, controlling their behavior.

   - **@Retention**: Specifies how long the annotation is retained (SOURCE, CLASS, RUNTIME).
     ```java
     @Retention(RetentionPolicy.RUNTIME)
     @interface MyAnnotation {
         String value();
     }
     ```

   - **@Target**: Specifies where an annotation can be applied (e.g., TYPE, METHOD, FIELD).
     ```java
     @Target(ElementType.METHOD)
     @interface MyMethodAnnotation {
         String description();
     }
     ```

   - **@Inherited**: Indicates that an annotation is inherited by subclasses.
     ```java
     @Inherited
     @Target(ElementType.TYPE)
     @Retention(RetentionPolicy.RUNTIME)
     @interface MyInheritedAnnotation {
         String info();
     }
     ```

   - **@Documented**: Indicates that an annotation should be included in the JavaDoc.
     ```java
     @Documented
     @Retention(RetentionPolicy.RUNTIME)
     @Target(ElementType.METHOD)
     @interface MyDocumentedAnnotation {
         String description();
     }
     ```

### <a name="custom-annotations"></a>**Custom Annotations** 
   - Developers can create custom annotations to suit their specific needs, defining elements similar to methods in an interface.

   - **Defining a Custom Annotation**:
     ```java
     @Retention(RetentionPolicy.RUNTIME)
     @Target(ElementType.METHOD)
     public @interface MyCustomAnnotation {
         String author();
         String date();
         int version() default 1;
     }
     ```

   - **Using a Custom Annotation**:
     ```java
     @MyCustomAnnotation(author = "John Doe", date = "2024-08-23", version = 2)
     public void myMethod() {
         System.out.println("Custom annotation example.");
     }
     ```

   - **Accessing Annotations via Reflection**:  
     ```java
     Method method = MyClass.class.getMethod("myMethod");
     MyCustomAnnotation annotation = method.getAnnotation(MyCustomAnnotation.class);

     if (annotation != null) {
         System.out.println("Author: " + annotation.author());
         System.out.println("Date: " + annotation.date());
         System.out.println("Version: " + annotation.version());
     }
     ```

### <a name="annotations-in-java-frameworks"></a>**Annotations in Java Frameworks**
   - **Spring**: Uses annotations like `@Component`, `@Autowired`, and `@RequestMapping` for dependency injection, bean definition, and web request handling.
   - **JUnit**: Uses annotations like `@Test`, `@Before`, and `@After` for unit testing.
   - **Hibernate**: Uses annotations like `@Entity`, `@Table`, and `@Id` for mapping Java classes to database tables.

---
