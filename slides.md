---
theme: default
background: >-
  https://images.unsplash.com/photo-1545486332-9e0999c535b2?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=387&q=80
class: text-center
highlighter: prism
lineNumbers: true
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
drawings:
  persist: false
transition: slide-left
css: unocss
title: Introduction to Unit Testing
---

# Introduction to Unit Testing
<br>
by Audrey Carmel Jay J. Nanual


---
transition: fade-out
layout: center
---

# What will we talk about today?
<br>

1. Unit testing theory (i.e., testing framework)
2. Getting started on testing
3. JUnit 5 - basics
4. JUnit 5 - more advanced concepts
5. Test-driven development (TDD)
6. Other testing frameworks

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
I will be covering these topics, which should give us a good grasp of what unit testing is all about.

We will discuss basic knowledge about unit testing (including what a testing framework is), what we should do to our project folder and files before the actual testing part, JUnit 5 concepts, what test-driven development or TDD is, and the different testing frameworks out there for Java.  

Without further ado, let's move on to the first one...
-->

---
transition: fade-out
layout: center
---

# 1. Theory Behind Unit Testing


<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #f279a6 10%, #ba3c66 20%);
  background-size: 100%;
  font-size: 100px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
...the basic theory or concepts about unit testing.
-->





---
transition: fade-out
layout: center
---

# 1.1. What are unit tests?
- Software tests at the lowest possible level
- Test single units of software

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 100px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
So what are unit tests? Would anyone like to describe what a unit test might be? 

***Wait for answer...***

Exactly. A unit test is a type of software testing where individual units or components of a larger software system are tested in isolation from the rest of the system.

In Java, these software units or components are typically methods or functions.

The goal of unit testing is to validate that each unit of the software performs as expected and meets its design specifications.
-->

---
transition: fade-out
layout: center
---

# 1.2. Are unit tests necessary? 
<br>

Unit tests are **NECESSARY** in every good piece of software!
- Increased confidence during development
- Cleaner, more reusable code
  - _"If you try to write unit tests for a class and you cannot do it, then chances are that your class design is all wrong."_
- Lower cost of mistakes

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Are unit tests necessary?

Short answer: _**YES**_.

Every good piece of software should have unit tests, and every software developer should write unit tests. If your project manager doesn't give you time to write unit tests, or you yourself don't give yourself time to write unit tests (even if it's just for personal projects), then most probably your software will have poor quality.

But how are they necessary?

1. Well, they somehow increase confidence during development. We know how unit tests are useful for catching and fixing bugs early in the software development process, right? So by testing individual units of the software in isolation, developers can identify and fix defects before they have a chance to propagate to other parts of the system. They also help ensure that changes to the codebase do not accidentally introduce new bugs or regressions.

2. Unit tests also make you write cleaner and more reusable code. I heard that the rule of thumb is as follows: "If you try to write unit tests for a class and you cannot do it, then chances are that your class design is all wrong."

3. Also, unit tests lower the cost of mistakes. It's much easier to fix a bug when you detect it early in the development rather than when your application is in production.
-->

---
transition: fade-out
layout: center
---

# 1.3. Who writes unit tests?

- Unit tests are typically written by **_software developers_** themselves.

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

p {
  color: #FFFFFF;
}
</style>

<!--
Who writes unit tests?

Well, they should be written by software developers while they create new features — **_NOT_** by software testers. The tests are then automated using a unit testing framework.
-->

---
transition: fade-out
layout: center
---

# 1.4. What is a testing framework?

- A set of tools and rules that help you test your computer program automatically
- **_JUnit 5_** – de facto standard framework for Java testing
  - often combined with other frameworks for complicated projects

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
A testing framework is a set of tools and rules that help you test your computer program automatically. It helps you check if your program is doing what you want it to do and if it's working the way it should. This way, if there are any mistakes or "bugs" in your program, you can catch them early and fix them before the program is used by other people.

What happens is: the software developers write small pieces of code called "tests" that check if a particular part of the program is working as expected. The tests are then run automatically by the testing framework, which checks if the results of the tests match what the programmer expects.

If the tests fail, the programmer can make adjustments to the code to fix the problem before the program is used by others. This ensures that the code works correctly and meets the needs of its users

In the world of Java, JUnit is the de facto standard for Java testing, but it is typically combined with other testing frameworks such as Mockito for complicated projects. The previous version of JUnit was JUnit 4, which was released as early as 2006. The latest version of JUnit is JUnit 5, which was released 11 years later in 2017.
-->

---
layout: center
---

# 1.5. Sample Test Unit
<br>

```ts {all|2-3|16-21|5-14|9|12|all}
// import statements
import org.junit.Test;
import static org.junit.Assert.*;

// test class
public class CalculatorTest {

    // a unit test
    @Test
    public void testAddition() {
        int result = Calculator.add(2, 3);
        assertEquals(5, result);
    }
}

// Calculator class
class Calculator {
    public static int add(int a, int b) {
        return a + b;
    }
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
This is a sample unit test for a simple Java Calculator program.

We have our import statements, our Calculator class containing an **_add()_** method, and our test class, which contains our test method.

Some lines and logic may seem unfamiliar to those who haven't delved into unit testing yet, but don't worry: we'll be understanding them throughout the presentation and hopefully by the end of it all, we'll be able to understand what they are and how they work.
-->

---
transition: fade-out
layout: center
---

# 2. Things to keep in mind before testing

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #f279a6 10%, #ba3c66 20%);
  background-size: 100%;
  font-size: 100px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Now let's move on to the things we need to keep in mind before we the actual testing part.
-->

---
transition: fade-out
layout: center
---

# 2.1. Create a Java project

- > **Ctrl + Shift + P**
- > Java: Create Java Project...
- Choose among the following build automation tools:
    - Maven
    - Gradle
    - Spring Boot
    - Quarkus
    - MicroProfile
    - JavaFX

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
If you want to create a Java project in VS Code using a build automation tool, you can just press **_Ctrl + Shift + P_**, click _"Java: Create Java Project..."_ and then choose among the available build automation tools there for Java projects, like Maven, Gradle, Spring Boot, Quarkus, MicroProfile, or JavaFX.

A build automation tool is essentially a software tool that helps automate the process of building and packaging software applications. It can be used to compile, test, and package the source code of an application into a distributable format. One nice thing about them is they create a template project structure for us, so we don't have to create the necessary folders and files from scratch everytime we make a software application. 

Each of these technologies has its own strengths and is used for different purposes. For example, Maven and Gradle are used for build automation and dependency management, Spring Boot and Quarkus are used for developing web and microservices, MicroProfile provides APIs for cloud-native development, and JavaFX is used for desktop and mobile application development. Whichever one you use will really depend on your project's needs.

............... **_ADDITIONAL INFO_** ...............

These are build automation tools for Java projects that help manage dependencies, build and package the code, and automate testing and deployment. Each of these technologies has its own strengths and is used for different purposes. For example, Maven and Gradle are used for build automation and dependency management, Spring Boot and Quarkus are used for developing web and microservices, MicroProfile provides APIs for cloud-native development, and JavaFX is used for desktop and mobile application development.

- **Maven:** Maven is a build automation tool that helps manage dependencies, build and package code, and automate testing and deployment in Java projects. It uses an XML-based configuration file called pom.xml to define the project structure, dependencies, and build process.

- **Gradle:** Gradle is a build automation tool similar to Maven but uses a more flexible and concise Groovy-based DSL for defining the build process. Gradle is highly customizable and can be used to build any type of project, from simple Java applications to complex multi-module projects.

-* *Spring Boot:** Spring Boot is an open-source framework that simplifies the development of web applications and microservices in Java. It provides a number of pre-configured modules that help developers quickly build and deploy applications with minimal configuration.

- **Quarkus:** Quarkus is a Kubernetes-native Java framework designed to make it easier to develop cloud-native applications. It provides a fast startup time, low memory footprint, and supports a wide range of popular Java frameworks and libraries.

- **MicroProfile:** MicroProfile is a set of open-source specifications for developing microservices in Java. It provides a number of APIs and technologies that help developers build cloud-native applications, including support for service discovery, fault tolerance, and distributed tracing.

- **JavaFX:** JavaFX is a platform for developing desktop and mobile applications in Java. It provides a rich set of UI controls and multimedia support, and can be used to build cross-platform applications for Windows, Mac, Linux, and mobile devices.
-->

---
transition: fade-out
layout: center
---

# 2.2. Standard Java project folder structure

<img src="/assets/images/project-folder-structure.png" class="m-10 h-90 rounded shadow"/>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
A Java project usually has the following folder structure:

- One (1) "**src**" folder, which typically refers to the source code folder. It is where developers typically place the source code files that make up the project.

    - Inside the "**src**" folder are the "**main**" and "**test**" folders, which are typically used to separate the production code from the test code.

- The "**test**" folder contains the test source code, which includes all the test classes and packages that are used to verify the functionality of the application. These test classes are typically written using a testing framework, such as JUnit, and they are designed to ensure that the code in the "main" folder works as expected.

    - Separating the main code from the test code helps to keep the project organized and maintainable. It's also easy to run the tests independently of the main code, and to keep track of which tests have been run and which ones still need to be run.

- The "**main**" and "**test**" folders each have "**java**" and "**resources**" folders.

    - The "**java**" folder contains all the Java source code files that are used to build the application. This includes all the Java classes, interfaces, enums, and other code that define the behavior and functionality of the application. The "**java**" folder may also contain subfolders to further organize the code.

    - The "**resources**" folder contains all the non-Java resources that the application needs, such as configuration files, properties files, images, and other assets. These resources are typically read by the Java code at runtime to customize the behavior of the application or to provide a better user experience. This folder may also contain subfolders to further organize the resources.
-->

---
transition: fade-out
layout: center
---

# 2.3. Create a test file (VS Code)

```ts {all|1|2-3|2|7|5-12|7-11|3|10|all}
// ClassTest.java
import org.junit.Test; // allows @Test
import static org.junit.Assert.*; // allows assertion methods

public class MyTest {

  @Test
  public void testMethod() {
    // Test codes here
    // e.g. assertTrue(), assertEquals(), etc.
  }
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
To create a test file in VS Code, you just create a new file in the "test" folder of your project, then save the file with a the name of the class being tested and add "Test.java" at the end. This naming convention is used by most testing frameworks to identify test files.

Add the necessary import statements at the top of the file to import the modules you need from you testing framework. For example, **_import org.junit.Test;_** allows you to use **@Test**, which is an annotation provided by the JUnit testing framework. This annotation is used to identify a method as a test method, which means that the method is responsible for verifying some aspect of the functionality of the code being tested. In short: the testing framework will automatically detect and run all methods annotated with @Test in the test class.

Then you write your test cases inside the test class. Again, each test case should be annotated with the "@Test" annotation and should call the methods in the class that you want to test, like in this code here.

You'll notice we have the **_import static org.junit.Assert.*_** statement, which allows us to access Assertion methods. The Assert class contains a set of static methods that are commonly used in JUnit test cases to perform assertions, which are statements that verify that a certain condition is true. We're going to discuss the most common Assert methods later on.
-->

---
transition: fade-out
layout: center
---

# 3. JUnit 5 - Basics

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #f279a6 10%, #ba3c66 20%);
  background-size: 100%;
  font-size: 100px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Let's move on to JUnit 5 Basics, where we'll go through the most commonly used Assert methods and annotations in Java unit testing.
-->





---
layout: center
---

# 3.1. Best Practices
<br>

```ts {all|3}
// Naming convention 1: "should...when..."
@Test
public void should_ReturnTrue_When_SumIsPositive() {
  // Given — initial conditions
  int x = -3;
  int y = 5;

  // When — where we invoke the method
  boolean sum = x + y;

  // Then — provide the assertion
  assertTrue(sum);
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
But first things first, let's discuss some good practices to apply when doing unit testing. First: naming conventions.

There are several common naming conventions for Java unit tests. One is following the "should...when..." pattern, such as in this unit test.
-->





---
layout: center
---

# 3.1. Best Practices
<br>

```ts {all|3|1|5|6-8|10-11|13-15}
Calculator calcu = new Calculator();

// Naming convention 2: "...test<MethodName>_Should<ExpectedBehavior>..."
@Test
public void testCalculateSum_ShouldReturnCorrectSum() {
  // Given 
  int num1 = 10;
  int num2 = 5;

  // When 
  int actualSum = calcu.calculateSum(num1, num2);

  // Then 
  int expectedSum = 15;
  assertEquals(15, sum);
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Another widely used convention is to name test methods using this pattern.

In this convention, the method name begins with the word "test" and is followed by the name of the method being tested, with the first letter of the method name capitalized. This is followed by the word "Should" and a brief description of the expected behavior of the method being tested, also with the first letter of each word capitalized.

For example, if you were testing from the Calculator class a method called calculateSum(), a test method using this convention might be named like this. This naming convention helps to make it clear what the purpose of each test method is, and what behavior it is testing for.

Another good practice is making sure your **unit tests are as clear as possible**, so that when someone else takes a look at your code, they immediately know what it does. One of the ways to make unit tests look clear and informative is to break them into three steps: **give**, **when**, **then**

"**_Given_**" are the initial conditions or the input values.

"**_When_**" is where we invoke the method under the test and usually store its result in a variable.

In the "**_then_**" part, we provide the assertion.
-->





---
layout: center
---

# 3.1. Best Practices
<br>

```ts {none|8|all|none}
@Test
public void should_ReturnTrue_When_SumIsPositive() {
  int x = -3;
  int y = 5;

  boolean sum = x + y;

  assertTrue(sum);  // opposite: assertFalse()
}
```

```ts {none|11|all|none}
Calculator calcu = new Calculator();

@Test
public void testCalculateSum_ShouldReturnCorrectSum() { 
  int num1 = 10;
  int num2 = 5;

  int actualSum = calcu.calculateSum(num1, num2);

  int expectedSum = 15;
  assertEquals(15, sum); // assertEquals(expectedValue, actualValue);
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
If you've noticed, we can see some words here that seem to be important to unit testing.

**assertTrue()** is a method provided by the JUnit testing framework. The assertTrue() method takes a single argument, which is a boolean expression that is expected to be true. If the expression is true, the test will pass. If the expression is false, the test will fail, and an error message will be displayed.

There is also an **assertFalse** method. It takes a single argument, which is a boolean expression that is expected to be false. If the expression is false, the test will pass. If the expression is true, the test will fail, and an error message will be displayed.

Then there's **assertEquals()**, which checks if two values are equal. It is typically used to compare the actual result of a test with the expected result.

The method takes two arguments: the expected value and the actual value. If the two values are equal, the test passes. If the values are not equal, the test fails and an error message is displayed.
-->





---
layout: center
---

# 3.2. Test exceptions
<br>

```ts {all|5|5-6|all}
public class DivideTest {
    
    @Test
    public void testDivideByZero() {
        assertThrows(ArithmeticException.class, () -> {
            int result = 5 / 0; // should throw an ArithmeticException
        });
    }
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
In Java programming, an Exception is an object that represents an abnormal condition or error that occurs during the execution of a program. When an exception occurs, it is thrown from the point at which the error occurred to a point where it can be handled by the program.

For example, an ArithmeticException is a specific type of Exception in Java that is thrown when an arithmetic operation, such as division by zero, is attempted and the result is not a finite number.

To test if a code throws an exception, we need to use **assertThrows()**, which is a method in the JUnit testing framework for Java that allows you to test if a specific piece of code throws an exception when it is run.

- So you first specify the expected exception type as the first parameter to **assertThrows()**.

- You provide a lambda expression as the second parameter to **assertThrows()**, which contains the code you want to test for the expected exception.

- **assertThrows()** runs the lambda expression and captures any exceptions thrown by the code.

- If the code throws an exception of the expected type, **assertThrows()** passes the test.

- If the code does not throw an exception of the expected type, or if it throws no exception at all, **assertThrows()** fails the test.

In this example, the **testDivideByZero()** method tests whether an ArithmeticException is thrown when attempting to divide by zero. The **assertThrows()** method expects an ArithmeticException to be thrown when executing the lambda expression that contains the division by zero.

If an ArithmeticException is thrown, the test passes. If an exception of a different type is thrown or no exception is thrown, the test fails. The failure message will indicate the type of exception that was thrown or that no exception was thrown.
-->





---
layout: center
---

# 3.3. Test with multiple assertions
<br>

```ts {all|10-16|12|13|14|15|all}
Calculator calcu = new Calculator();

@Test
public void testCalculateSum() {
  int num1 = 2;
  int num2 = 5;

  int result = num1 + num2;

  // multiple assertions
  assertAll("Addition test",
    () -> assertEquals(5, result),
    () -> assertNotNull(result),
    () -> assertTrue(result > 0),
    () -> assertNotEquals(6, result)
  );
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Sometimes there are situations where we want to run a test method with multiple assertions. We can do this with assertAll(), is also a method provided by JUnit 5's Assertions class. It allows you to group multiple assertions together in a single test case.

When multiple assertions are combined using assertAll(), all of them are executed and their results are collected before any failures are reported.

This means that if there are multiple assertions in a test case, even if the first assertion fails, the subsequent assertions will still be executed and their results will be reported.
-->






---
layout: center
---

# 3.4. Test null values
<br>

```ts {all|4|4-5|all}
@Test
public void testString() {

  String str = "there is something here";
  assertNull(str);
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Then we have assertNull(), which is a method that allows you to test if a value is null. It takes a single argument of type Object and checks if the argument is null. If the argument is null, the test passes; if the argument is not null, the test fails and an AssertionError is thrown.

In this example, we declare a variable str and assign it the value of a string that says "there is something here". So it's not null. If we pass it to assertNull() the test fails because str is not null.

On the other hand, if str was indeed null, the test would pass.
-->

---
layout: center
---

# 3.5. Test array equality
<br>

```ts {all|3-4|6|all}
public void testArrayEquality() {

  int[] expected = {1, 2, 3};
  int[] actual = {1, 2, 3};

  assertArrayEquals(expected, actual);
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
We also have assertArrayEquals(), which allows you to compare two arrays and check if they are equal.

The assertArrayEquals() method takes two arguments: expecteds and actuals. Both arguments must be arrays of the same type. If the arrays are not of the same type, an AssertionError will be thrown.

The assertArrayEquals() method compares each element in the expecteds array to the corresponding element in the actuals array. If all elements match, the test passes. If any element does not match, the test fails and an AssertionError is thrown.

Here is an example of how you can use assertArrayEquals() in a unit test. In this example, we declare two arrays expected and actual containing the same values. We then use assertArrayEquals(expected, actual) to compare the two arrays. Since all elements in expected match the corresponding elements in actual, the test passes.

On the other hand, if actual contained a different value than expected, the test would fail with an AssertionError:
-->





---
layout: center
---

# 3.6. @BeforeEach

```ts {all|8|8-11|13-17|19-23|all}
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;

public class CalculatorTest {

  private Calculator calculator;

  @BeforeEach
  public void setUp() {
    calculator = new Calculator();
  }

  @Test
  public void testAddition() {
    int result = calculator.add(2, 3);
    assertEquals(5, result);
  }

  @Test
  public void testSubtraction() {
    int result = calculator.subtract(5, 3);
    assertEquals(2, result);
  }
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
In Java unit testing, @BeforeEach is a JUnit annotation used to denote a method that is executed before each test method is run. It is used to set up the test environment, including creating objects, initializing variables, or preparing test data that is required for the test method to execute.

When a test class is executed, JUnit runs the method annotated with @BeforeEach before executing each test method in the class. This ensures that the test environment is initialized consistently before each test is run, and any changes made by one test method do not affect the next test method.

Here is an example of how @BeforeEach can be used in a Java unit test...

In this example, the @BeforeEach annotated setUp() method creates a new instance of the Calculator class before each test method is run. This ensures that the calculator object is initialized consistently before each test, and any changes made by one test method do not affect the next test method.
-->





---
layout: center
---

# 3.7. @AfterEach

```ts {all|10|10-13|all}
public class CalculatorTest {

  private Calculator calculator;

  @BeforeEach
  public void setUp() {
    calculator = new Calculator();
  }

  @AfterEach
  public void tearDown() {
    calculator = null;
  }

  @Test
  public void testAddition() {
    int result = calculator.add(2, 3);
    assertEquals(5, result);
  }

  @Test
  public void testSubtraction() {
    int result = calculator.subtract(5, 3);
    assertEquals(2, result);
  }
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Then @AfterEach is a JUnit annotation used to denote a method that is executed after each test method is run. It is used to clean up the test environment, including releasing resources, closing connections, or deleting temporary data that was created during the test.

When a test class is executed, JUnit runs the method annotated with @AfterEach after executing each test method in the class. This ensures that the test environment is cleaned up consistently after each test is run, and any changes made by one test method do not affect the next test method.

Let's piggyback on the previous example and add an @AfterEach-annotated test method...

In this example, the @AfterEach-annotated tearDown() method resets the value of the Calculator instance to null after each test method is run.
-->





---
layout: center
---

# 3.8. @BeforeAll

```ts {all|4|1|9-12|14-17|4-7|6|all}
public class MyTest {
  private static int number;

  @BeforeAll
  public static void setUp() {
    number = 10;
  }

  @Test
  public void testNumberIsPositive() {
    assertTrue(number > 0);
  }

    @Test
  public void testNumberIsEven() {
    assertTrue(number % 2 == 0);
  }
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
@BeforeAll is a JUnit annotation used to indicate a method that should be executed once before any test cases in the class are run. It is typically used to set up the test environment or to perform some common tasks required for all the test cases in the test suite.

The @BeforeAll annotation is typically used to set up the test environment or to perform some common tasks required for all the test cases in the test suite. For example, you might use it to initialize a database connection or to load some data that is needed for all the tests.

Here's a sample Java unit test code using @BeforeAll...

we have a class called MyTest that contains two test methods: testNumberIsPositive() and testNumberIsEven(). Before running any of these test methods, the setUp() method is executed once, and it sets the value of the number variable to 10.

The first test method, testNumberIsPositive(), uses the assertTrue() assertion to check if the value of number is positive. The second test method, testNumberIsEven(), uses the assertTrue() assertion to check if the value of number is even.

Since @BeforeAll is used to set up the test environment or to perform some common tasks required for all the test cases in the test suite, we used it in this example to initialize the value of number before any test method is executed.

.................. **ADDITIONAL INFO** ..................

@BeforeAll can only be used on static methods and can be used with any access modifier. It is important to note that the @BeforeAll method should not depend on the state of any other test methods or previous test runs, as it will only be executed once.

@BeforeAll and @BeforeEach are two JUnit annotations used in Java unit testing to execute methods before running tests. The main difference between them is when they are executed.

@BeforeAll is executed once before all the test methods in a test class are executed. It is typically used for expensive setup operations that need to be performed only once, such as initializing a database connection or loading a large dataset.

@BeforeEach, on the other hand, is executed before each test method in a test class. It is typically used for setting up the test environment and ensuring that each test is run in a clean and consistent state.
-->





---
layout: center
---

##### 3.9. @AfterAll

```ts {all|2-3|all}
public class MyTest {
  private static int number;

  @AfterAll
  public static void tearDownAll() {
    System.out.println("Cleaning up all tests");
  }

  @AfterEach
  public void tearDown() {
    number = 0;
    System.out.println("Cleaning up a test");
  }

  @Test
  public void testNumberIsPositive() {
    number = 10;
    assertTrue(number > 0);
    System.out.println("System.out.println("Running testNumberIsPositive");
  }

  @Test
  public void testNumberIsEven() {
    number = 11;
    assertTrue(number % 2 == 0);
    System.out.println("System.out.println("Running testNumberIsEven");
  }
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h5 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
@AfterAll is a JUnit annotation in Java unit testing used to mark a method that will be executed once after all the tests in a test class have been run. This annotation can be used to clean up the resources used in the tests or to perform any necessary teardown tasks. This can include closing database connections, deleting temporary files or directories, or shutting down servers.

In the left example, we have two test methods: testNumberIsPositive() and testNumberIsEven(). We also have two teardown methods: tearDownAll() annotated with @AfterAll and tearDown() annotated with @AfterEach.
When we run this test class, the tearDownAll() method will be executed once after all the test methods are run. This method prints a message to the console.

After each test method is run, the tearDown() method will be executed. This method sets the value of number to 0 and prints a message to the console.

When we run the test methods, we can see from the console output that the tearDownAll() method is executed only once, while the tearDown() method is executed twice (once after each test method).

In summary, @AfterAll is executed once after all the test methods in a test class, while @AfterEach is executed after each test method in a test class. Use @AfterAll for expensive teardown operations that need to be performed only once, and use @AfterEach for cleaning up the test environment and ensuring that each test is run in a clean and consistent state.


.................. **ADDITIONAL INFO** ..................

@AfterEach VS @AfterAll

@AfterAll and @AfterEach are two JUnit annotations in Java unit testing used to execute methods after running tests. The main difference between them is when they are executed.

@AfterAll is executed once after all the test methods in a test class are executed. It is typically used for expensive teardown operations that need to be performed only once, such as closing a database connection or deleting a large dataset.

@AfterEach, on the other hand, is executed after each test method in a test class. It is typically used for cleaning up the test environment and ensuring that each test is run in a clean and consistent state.
-->

---
transition: fade-out
layout: center
---

# 4. JUnit 5 - More Advanced Concepts

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #f279a6 10%, #ba3c66 20%);
  background-size: 100%;
  font-size: 100px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Now let's discuss more annotations and assert methods.
-->





---
layout: center
---

# 4.1. Parameterized Tests – @ValueSource
<br>

```ts {all|2|1|1-2|3-5|all}
@Parameterized test
@ValueSource(ints = {1, 2, 3})
void testIsPositive(int number) {
  assertTrue(number > 0);
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
In Java unit testing, a parameterized test is a type of test where the same test logic is executed multiple times with different input parameters. The input parameters can be defined as an array or a collection of values, and the test code is executed once for each input parameter. 

There are many ways to provide these values. For this slide, we're going to cover the simplest case where we only change a single value each time a test is run, which can be done through the @ValueSource annotation.

The @ValueSource annotation allows you to specify an array of values that will be used as input to the parameterized test method. For example, consider the following test method...

The @ParameterizedTest annotation tells JUnit that this is a parameterized test method, and the @ValueSource annotation provides a list of integer values that will be used as input to the testIsPositive method. During the test execution, JUnit will run this test method three times, once with each value specified in the @ValueSource array. In each iteration, the value will be passed as an argument to the testIsPositive method.
-->





---
layout: center
---

# 4.2. Parameterized Tests – @CsvSource
<br>

```ts {all|8|7|1-4|8|9-11|all}
// add() method
public int add(int a, int b) {
  return a + b;
}

// test method for add()
@ParameterizedTest
@CsvSource({"6, 2, 8", "5, 0, 5", "1, 1, 2"})
public void testAdd(int a, int b, int expected) {
  assertEquals(expected, add(a, b));
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Then we have the @CsvSource annotation, which allows us to provide multiple values as input to the test method in each test run.

The "@CsvSource" annotation is also used with the "@ParameterizedTest" annotation, which indicates that the test method should be run multiple times with different input values. The string array passed to the "@CsvSource" annotation contains the test data that will be used to run the test method multiple times.

For example, suppose you have a method that adds two integers and returns the result. You can use the "@ParameterizedTest" and "@CsvSource" annotations to test this method with multiple input values...

In this example, the "@CsvSource" annotation provides three sets of input values, each containing two integers and the expected result of adding them. The test method is run three times, once with each set of input values, and the "assertEquals" method is used to check that the actual result of adding the two integers matches the expected result.

By using the "@CsvSource" annotation, you can easily provide a large amount of test data to your test methods without having to hard-code each test case individually.
-->





---
layout: center
---

# 4.3. Parameterized Tests – @CsvFileSource
<br>

```ts {all|2-5|2|3-5|9|8-11|all}
// content inside CSV file
input1, input2, expectedOutput
1, 1, 2
2, 3, 5
-1, -1, -2

// test method
@ParameterizedTest
@CsvFileSource(resources = "/test-data.csv")
public void testAdd(int a, int b, int expected) {
  assertEquals(expected, add(a, b));
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
@CsvFileSource is used to provide input data for parameterized tests from a CSV file, which basically contains comma-separated values. The first row of the CSV file usually contains the column headers, and each subsequent row represents a set of input parameters for the test.

It is in the @CsvFileSource annotation where you specify the location of the CSV file containing the test data.

It then maps the CSV file data to the test method parameters based on their position in the file. In this example, the first column maps to input1, the second column maps to input2, and the third column maps to expectedOutput.

JUnit executes the annotated test method multiple times, once for each set of input parameters provided by the CSV file. During each iteration, JUnit passes the input parameters to the test method and executes the test logic. If the expected output matches the actual output, the test passes; otherwise, the test fails.
-->





---
layout: center
---

# 4.4. Repeated Tests – @RepeatedTest
<br>

```ts {all|1|all}
@RepeatedTest(5)
public void myRepeatedTest() {
  assertEquals(2 + 2, 4);
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
The @RepeatedTest annotation is used to repeat the execution of a test method a specified number of times. It takes an integer value as a parameter, which specifies the number of times the test method should be repeated. Each repetition is treated as a separate unit test.

For example, this code snippet demonstrates how to use @RepeatedTest to repeat the execution of a test method five times...

The myRepeatedTest() method will basically be executed five times, and each time the assertEquals() method will be called to verify that the sum of 2 and 2 is equal to 4.
-->





---
layout: center
---

# 4.5. Test Performance – assertTimeout()
<br>

```ts {all|8|all}
@Test
public void testMethod() {
  int num1 = 10;
  int num2 = 100;

  int product = num1 * num2;

  assertTimeout(Duration.ofSeconds(1), product);
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
The @assertTimeout annotation is used to test the execution time of a piece of code. It allows you to specify a timeout duration, after which the test will fail if the code being tested has not completed within that time limit.

Here is an example of how to use @assertTimeout in a test method...

The testMethod() contains the code to be tested, which is simply multiplying 10 and 100. The assertTimeout() method is used to wrap this code, and a timeout duration of 1 second is specified using Duration.ofSeconds(1).

When the test is run, assertTimeout() will execute the code and measure its execution time. If the code completes within the timeout duration, the test will pass. Otherwise, the test will fail and an exception will be thrown.
-->






---
layout: center
---

# 4.6.1. Assumptions – assumeTrue()
<br>

```ts {all|3|all}
@Test
public void testMethod() {
  assumeTrue(2 + 2 = 4);
  assertEquals(2 + 2, 4);
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
You may need to write some unit tests that only make sense under certain conditions. A very typical use case is when you have more than one execution environment.

For instance, when you run the project from your local machine while you develop code, this could be your dev environment. However, at some point you may want to move your project into production, so your environment may be prod. 

Basically some unit tests may not make sense in certain environments. You may only want to run some performance unit tests when you are in the prod environment because this is where you have powerful machines available. When you run unit tests on your local machine in the dev environment, you would like to skip such tests because you know your computer can be too weak to pass them.

These are when Assumptions are useful because if they are not true, the test is simply skipped but not failed. We have a lot of Assumption commands we can use, like assumeTrue().

In this example, the assumeTrue() method is used to check if the condition 2 + 2 == 4 is true. Since the condition is true, the assertEquals() method is executed and the test passes. However, if the condition were false, the test would be skipped and marked as a "skipped" test rather than a "failed" test.

The assumeTrue() method is useful for skipping tests that cannot be run under certain conditions. For example, if a test requires a certain system configuration or environment variable to be set, you can use assumeTrue() to skip the test if the condition is not met, rather than letting the test fail.
-->






---
layout: center
---

# 4.6.2. Assumptions – assumeFalse()
<br>

```ts {all|3|all}
@Test
public void testMethod() {
  assumeFalse(5 - 0 = 10);
  assertEquals(2 + 2, 4);
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Same with assumeFalse().

Here, the assumeFalse() method is used to check if the condition 2 + 2 == 5 is false. Since the condition is false, the assertEquals() method is executed and the test passes. However, if the condition were true, the test would be skipped and marked as a "skipped" test rather than a "failed" test.

-->





---
layout: center
---

# 4.6.3. Assumptions – assumeNotNull()
<br>

```ts {all}
assumeNotNull(obj1, obj2, obj3)
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
assumeNotNull() is a method is used to skip a test if any of the supplied objects is null.
-->






---
layout: center
---

# 4.6.4. Assumptions – assumeNoException()
<br>

```ts {all}
assumeNoException(() - {
  // code to be executed
});
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Then assumeNoException() is a method used to skip a test if the supplied executable (or basically function) throws an exception.
-->






---
layout: center
---

# 4.7. Organize your code with @Nested
<br>

```ts {all|3-6|8-20|11-14|16-20|8-20|all}
public class MyTest {
  
  @Test
  void test1() {
    // test something
  }

  @Nested
  class NestedTest {

    @Test
    void test2() {
      // test another thing
    }

    @Test
    void test3() {
      // test something else
    }
  }
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
The @Nested annotation is a feature introduced in JUnit 5 that allows you to create inner test classes within a test class. This annotation is useful when you want to group together related tests, create a hierarchy of tests, or simply organize your tests in a more readable manner.

To use the @Nested annotation, you simply define an inner class within your test class and annotate it with @Nested.

In this example, we have a test class called _MyTest_ that contains one test method (test1). We have also defined an inner class NestedTest and annotated it with @Nested. This inner class contains two more test methods (test2 and test3).

When you run this test class, JUnit 5 will treat the NestedTest class as a separate test class and run its test methods independently of the MyTest class. This means that you can use all of the same annotations and assertions in your nested test class as you would in your top-level test class.

So @Nested annotation is a powerful feature of JUnit 5 that allows you to create more expressive and organized test classes. It's especially useful when you need to group related tests together or share setup and teardown code in a fine-grained manner.
-->





---
layout: center
---

# 4.8.1. Other Common Annotations – @DisplayName
<br>

```ts {all|2|all}
@Test
@DisplayName("Custom test display name")
void testMethod() {
    // test code here
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Now we just have three more annotations left to discuss.

The @DisplayName annotation is a feature introduced in JUnit 5 that allows you to provide a custom display name for your test classes and test methods. This can make your test results more readable and easier to understand, especially when you have complex or numerous tests.

In this example, the @DisplayName annotation is used to set the display name of the testMethod() to "Custom test display name". When you run the test, this custom display name will be shown in the test results instead of the default method name.
-->





---
layout: center
---

# 4.8.2. Other Common Annotations – @Disabled
<br>

```ts {all|2|all}
@Test
@Disabled("This test is not yet implemented")
void testMethod() {
  // test code here
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Then we have the @Disabled annotation, which you can use to ignore a test. Such a test will not be executed and it will never fail or pass. The test will basically be skipped.

So just imagine that you have a valid unit test. One day, something in your code changes temporarily, and you want to deactivate the test for a short period. You can annotate those specific components with @Disabled. This annotation can be used in scenarios where a test is not yet implemented, when a test is known to fail, or when you want to temporarily disable a test that is failing due to external factors such as an unstable environment.

In this example, the testMethod() is annotated with @Disabled and provided with a custom message indicating that the test is not yet implemented. When you run the tests, JUnit will skip over this test and not execute it.
-->





---
layout: center
---

# 4.8.3. Other Common Annotations – @DisabledOnOS
<br>

```ts {all|2|all}
@Test
@DisabledOnOs(OS.WINDOWS)
void testMethod() {
    // test code here
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Then we have @DisabledOnOS(), which allows you to disable a test method or a test class on a specific operating system. This can be useful when you have tests that are not compatible with certain operating systems or when you want to skip tests on certain platforms.

In this example, the testMethod() is annotated with @DisabledOnOs and provided with the OS.WINDOWS constant. This means that the test will be disabled when running on a Windows operating system.
-->





---
layout: center
---

# Assertions | Annotations | Assumptions
<br>

```ts {all|1-7|9-16|18-22|all}
// Assertions
assertTrue();
assertFalse();
assertAll();
assertNull();
assertArrayEquals();
assertTimeout();

// Annotations
@Test
@BeforeEach @AfterEach @BeforeAll @AfterAll
@ParameterizedTest @ValueSource @CsvSource @CsvFileSource
@RepeatedTest
@Nested
@DisplayName
@Disabled @DisabledOnOS

// Assumptions
assumeTrue();
assumeFalse();
assumeNotNull();
assumeNoException();
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
So just to clarify in case there's some confusion... assertions, annotations, and assumptions are all important features in JUnit 5, but they serve different purposes.

**Assertions** are used to verify that expected values match actual values in your test cases. They typically used within the body of a test method to validate the results of the test.

**Annotations** are used to provide metadata about your test classes and test methods. They are used to configure JUnit 5's behavior for your tests, such as specifying which methods to execute before or after each test, disabling certain tests, or specifying timeout values for test execution.

Assumptions are used to check assumptions about the environment in which your test is running. If the assumption fails, the test will be skipped, but it will not fail. This can be useful when you want to skip a test if certain preconditions are not met. They are typically used at the beginning of a test method to check that certain conditions are met before the actual test is run.
-->





---
layout: center
---

# withdrawAmount() method from ATM system
<br>

```ts {all|6-8|10-12|14-18|all}
public void withdrawAmount(double amountToWithdraw) {

  // amount to be withdrawn must be divisible by at least 20 (since 20 is the smallest Philippine bill)
  if (amountToWithdraw % 50 == 0 || amountToWithdraw % 20 == 0) {

      // if inputted amount is greater than current balance, withdraw operation is denied
      if (amountToWithdraw > atm.getBalance()) {
          System.out.println("\nInsufficient balance.\n");
      
      // if inputted amount is 0, withdraw operation is denied
      } else if (amountToWithdraw == 0) {
          System.out.println("\nInvalid value.\n");

      } else {
          accountStatement.put(amountToWithdraw, " withdrawn."); // add this statement to transaction history
          atm.setBalance(atm.getBalance() - amountToWithdraw); // subtract inputted amount from current balance
          System.out.println("\n" + Utilities.moneyFormat(amountToWithdraw) + " withrawn successfully.\nCollect your cash.\n");
          viewBalance();
      }
  } else {
      System.out.println("\nThe ATM can only give out banknotes.\n");
  }
}
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
original function
-->





---
layout: center
---

# Test methods for withdrawAmount()

```ts {all|3-6|8-12|15-19|22-26|all}
public class ATMInterfaceImplTest {

  // unit tests for the withdrawAmount() function
  @Nested
  @DisplayName("Unit tests for the withdrawAmount() function")
  class WithdrawTest {

    @Test // test if amountToWithdraw is more than the current balance
    public void testWithdrawAmount_IfAmountIsMoreThanBalance() {
        ATMInterfaceImpl atmInterfaceImpl = new ATMInterfaceImpl();
        atmInterfaceImpl.withdrawAmount(1000);
        assertEquals("Insufficient balance.", "Insufficient balance.");
    }

    @Test // test if amountToWithdraw is 0
    public void testWithdrawAmount_IfAmountIsZero() {
        ATMInterfaceImpl atmInterfaceImpl = new ATMInterfaceImpl();
        atmInterfaceImpl.withdrawAmount(0);
        assertEquals("Invalid value.", "Invalid value.");
    }

    @Test // test if amountToWithdraw is divisible by 20 or 50
    public void testWithdrawAmount_IfAmountIsNotDivisibleBy20Or50() {
        ATMInterfaceImpl atmInterfaceImpl = new ATMInterfaceImpl();
        atmInterfaceImpl.withdrawAmount(25);
        assertEquals("The ATM can only give out banknotes.", "The ATM can only give out banknotes.");
```

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #abde78 10%, #6ca632 20%);
  background-size: 100%;
  font-size: 34px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
original function
-->







---
transition: fade-out
layout: center
---

# 5. Test-Driven Development (TDD)
<br>
A software development approach where tests are written before the code is written.

1. Write a test.
2. Write code
3. Run the test.
4. Refactor.

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #f279a6 10%, #ba3c66 20%);
  background-size: 100%;
  font-size: 100px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Test-driven development (TDD) is a software development approach where tests are written before the code is written. The process typically involves the steps shown here:

1. **Write a test:** The developer writes a test that describes the functionality they want to implement. This test initially fails since the implementation does not exist yet.

2. **Write code:** The developer writes the minimum amount of code necessary to pass the test.

3. **Run the test:** The developer runs the test to ensure that it passes. If it does not pass, they revise the code until the test passes.

4. **Refactor:** The developer refactors the code to improve its design and maintainability.

This process is repeated for each new feature or change to the code. The goal of TDD is to ensure that the code is thoroughly tested and that the tests can catch any errors or bugs that may arise.

By writing tests first, TDD ensures that the developer focuses on the requirements of the code before writing the implementation. TDD also encourages the developer to write code that is modular, extensible, and easy to maintain.
-->





---
transition: fade-out
layout: center
---

# 6. Other Testing Frameworks

- JUnit Pioneer
- AssertJ
- Data Faker
- Mockito
- Easy Random
- Easy Random JUnit Extension
- Database Rider
- ModelAssert
- SpringFramework Testing
- Spring Boot Testing
- TestContainers
- Instancio
- Selenide
- JetBrains Aqua
- Vitest in Node.js

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #f279a6 10%, #ba3c66 20%);
  background-size: 100%;
  font-size: 100px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
- **_JUnit 5_**: A testing framework for Java that provides a powerful and flexible platform for writing and running unit tests.

- **_JUnit Pioneer_**: An open-source testing framework for Java that aims to simplify and improve the testing experience for developers.

- **_AssertJ_**: A fluent assertion library for Java that provides more readable and maintainable assertions for unit tests.

- **_Data Faker_**: A library for generating fake data for testing and development purposes.

- **_Mockito_**: A mocking framework for Java that enables the creation of mock objects in unit tests.

- **_Easy Random_**: A library for generating random data for testing and development purposes.

- **_Easy Random JUnit Extension_**: A JUnit extension that integrates Easy Random with JUnit 5 to simplify the creation of test data.

- **_Database Rider_**: A testing framework for Java that provides tools for managing and executing database tests.

- **_ModelAssert_**: A library for performing assertions on Java objects based on their properties and fields.

- **_SpringFramework Testing_**: A testing framework for Spring-based applications that provides tools for unit, integration, and end-to-end testing.

- **_Spring Boot Testing_**: A testing framework for Spring Boot-based applications that provides tools for testing Spring Boot features and components.

- **_TestContainers_**: A Java library that provides lightweight, disposable test containers to run tests against various infrastructure components like databases, message queues, and web services.

- **_Instancio_**: A lightweight and extensible testing framework for Java that provides a simple and intuitive API for writing tests.

- **_Selenide_**: A testing framework for web applications that provides a concise and expressive API for writing automated UI tests using Selenium WebDriver.

- **_JetBrains Aqua_**: A testing framework for Kotlin that provides tools for unit, integration, and UI testing.

- **_Vitest in Node.js_**: A testing framework for Node.js that provides tools for unit and integration testing, mocking, and code coverage analysis.
-->





---
transition: fade-out
layout: end
---

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #f279a6 10%, #ba3c66 20%);
  background-size: 100%;
  font-size: 100px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
end
-->
