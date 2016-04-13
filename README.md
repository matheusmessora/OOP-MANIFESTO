# OOP-MANIFESTO
10 basic rules to increase your Object Oriented Programming skills.
Keep practicing and follow ALL the rules. Your skills should increase. 

Based on [The ThoughtWorks Anthology: Essays on Software](http://www.amazon.com/The-ThoughtWorks-Anthology-Technology-Programmers/dp/193435614X)

## What are we looking for?
Every interview asks the same question. *When you are coding, what are the key concepts of good programming?*

This are some of the important ones:

- Loose coupling
- High cohesion
- Write testable classes, which is easily testable
- Composition over Iheritence
- Try stick to the open/close principle.
- KISS: Keep It Simple Stupid!


## The Rules
**1- One level of Identation per method**

```java
public void method() {
   int a = 0;
   if(a > 0) {
      if(a > 10) { 
         a++; // This is WRONG
      }
   }
}
```
+ Increase Readability
+ Decrease Complexity level

**2- Do not use the 'else' keyword.**

*When a given method provides one behavior for the if branch, and another behavior for the else branch, then it means that this particular method is not cohesive. It has got more than one responsibility, dealing with different behaviors.*

```java
public boolean method() {
   int years = 35;
   if(years > 21) {
     return true;
   } else { // This is WRONG
     return false; 
   }
}
```

+ Increase Single Responsability Principle

**3- Wrap primitive types, strings and Lists**

*If a variable of a primitive type has behavior, consider creating a class for it.*

```java
public class Account {
   int balance; // Wrong
   Balance balance; // Correct
   
   List<Customer> custommers;  // This is WRONG
   Custommers custommers;      // This is RIGHT
}

public class Balance {}

public class Custommers { 
   private List<Customer> custommersList;
   ...
}
```

+ Increase coesion
+ Increase Single Responsability Principle

**4- Use only one dot per line**

*Based on the  [Law of Demeter] (http://www.ccs.neu.edu/research/demeter/demeter-method/LawOfDemeter/paper-boy/demeter.pdf).*
*"Only talk to your friends"*
```java
public class Bank {
    Customer customer;

  // This is WRONG
   public void withdraw() {
      int value = customer.getBalance().value(); // WRONG
      if(value > 0) {
         customer.getBalance().withdraw(10);
      }
   }
   
   // This is RIGHT
   public void withdraw() {
      customer.withdraw(10);
   }
}
```
+ Better real world scenario
+ Bank is de-coupled from Customer.getBalance() Class/methods
+ Readability

**5- Do not abbreviate**
+ Increase Readability

**6- Keep your classes small**

A class should have 50 statements and 150 width length.

This excludes blank lines, comments and structure closing lines.
The code should be visible inside the text editor of your IDE.

In some languages, this also exclude the imports statements.

**7- Do not use classes with several instance variables**

:fire: This is polemical, and very hard to achieve :fire:

A class should have only **2 instances** variables.

```java
// This is WRONG
public class Customer {
    Long id;
    String email;
    String username;
    String password;
}

// This is RIGHT
public class Customer {
   Long id;
   CustomerDetails details;
}

public class CustomerDetails {
   Email email;
   Credentials credentials;
}
public class Credentials {
   String username;
   String password;
}
```
+ Increase coesion
+ This helps resolve the 3th and 6th rule, and vice-versa.

**8- Do not use static methods**

[Can you **simple** mock a static method?] (https://dzone.com/articles/why-static-bad-and-how-avoid)

It makes you loose the Polymorphism.

It is extreme hard to test.

[They aren't associated with any object. They really aren't methods at all, according to the usual definition. They are really just procedures.](http://stackoverflow.com/questions/4002201/why-arent-static-methods-considered-good-oo-practice)

+ Increase readability
+ Increase Polymorphism
+ Increase Testability

**9- Methods must have a maximum of 7 statements**

PAY Attention: A FOR statement counts as 3 statements.

*for (int i = 0; i < array.length; i++) {}*
 
This leads to:

**1**: int i = 0

**2**: i < array.length;

**3**: i++

**10- Use composition instead of inheritance**

Remember the 7th rule o achieve this one.

You should only use 2 instance variable per class. 

## Conclusion

The 7th rule is the core of the manifesto. All the others rules are here to help you with the 7th rule. It makes your code become extremely cohesive.

The loose couple idea is granted by the 3th, 4th 6th and 6th rule.



# EPIC TOPICS
In the word of [Fabio Sales Souza](https://github.com/fabiodoaraujo)
> Não estude para passar na prova, estude para aprender!
