# OOP-MANIFEST

Based on The ThoughtWorks Anthology: Essays on Software

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

+ Increase readability

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

**3- Wrap primitive types and strings**
*Basically, if a variable of a primitive type has behavior, consider creating a class for it.*

```java
public class Bank {
   int balance; // Wrong
   Balance balance; // Correct
}
```

**4- Use only one dot per line**
*Based on the  Law of Demeter. "Only talk to your friends"*
```java
public class Bank {
    Balance balance;

   public Balance getBalance(){ return balance; }

   public void method() {
      this.getBalance().isPositive(); // WRONG
      this.isBalancePositive(); // Correct
   }

   ...
}
```

**5- Do not abbreviate**

**6- Keep your classes small**
A class should have 50 statements. This excludes blank lines, comments and structure closing lines.
The code should be visible inside the text editor of your IDE.

**7- Do not use classes with several instance variables**
A class should have only 2 instance variables.

**8- Do not use static methods**
Can you simple mock a static method without frameworks?
https://dzone.com/articles/why-static-bad-and-how-avoid
