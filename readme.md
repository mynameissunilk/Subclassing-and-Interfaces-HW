---
title: Subclassing and Interfaces
type: Homework
duration: "1:00"
creator:
    name: Charlie Drews
    city: NYC
---

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Subclassing, Abstract Classes, and Interfaces

> ***Note:*** _You can discuss with classmates, but everyone must submit their own answers_

## Exercise

#### Requirements

- Fork this repo, then add your answers direcly to this **readme.md** file
  - After forking, you can clone, edit the readme in the text editor of your choice, and push back to Github...
  - Or, you can edit the readme [right from the browser](https://help.github.com/articles/editing-files-in-your-repository/)
- After adding your answers, submit a **pull request**

#### Questions

1. What is the difference between *member variables* (also called *instance variables*) and *class variables* (w/ keyword `static`)? Which can be accessed without creating an instance of the class?

2. Does it make sense to write  *getter* and *setter* methods for a `public` member variable? What about `private` variables?
   For public members, it makes less sense to use getters and setters, because these variables can be accessed directly. for example "object.membervariable = somevalue;" is possible with public variables. With private members, however, it makes sense to use getters and setters, as these methods can access the private variables that live in their class. 

3. What are some benefits of making member variables `private`?
   Private members cannot be accessed by classes/objects or methods from *outside* its class. This helps to ensure that these variables are not accidentally altered either while editing, or potentially due to an unforseen runtime bug. 

4. If class A extends class B, which is the super class and which is the sub class? Which would you call parent, and which would you call child?
   Class B is the superclass, and class A is the subclass, So you would call Class B the parent, and Class A the child. 

5. What does it mean for a class to *inherit* methods and/or variables from its parent class?
   Class A will inherit the member variables and methods of Class B. Optionally, Class A can make use of (or even extend) Class B's constructors. 

6. Consider the following code, where class Refrigerator extends class Appliance, and `getTemperature()` is a method in Refrigertor, but NOT in Appliance:
  ```
  Appliance myAppliance = new Refrigerator();
  double temperature = myAppliance.getTemperature();
  ```
  Why will this call to `getTemperature()` cause an error? How will *casting* help solve this issue?
      Assuming that getTemperature() does not return a double, we can write: "(double)myAppliance.getTemperature()" to convert the return type to a double. 

7. In a normal class (also called a *concrete* class), do you need to *implement* all of the methods, or can your simply *declare* some? What about in an `abstract` class?
   Assuming "implement" means writing more than the method signature (and not using an interface of abstract classes), then yes, concrete methods require a method with a block for its relevant code.. Abstract methods are only declared without blocks, either in an abstract class, or as members of an interface. 

8. What about an `interface`? Can you implement any methods in an interface? Can you declare methods in an interface?
   You only declare methods in an interface, and you fully implement them in the class that implements the interface-in-question. 
   An interface is only for storing abstract methods. They aren't fully implemented. abstract methods in interfaces are sort of outlines of methods to be specifically implemented in the classes that use them.
   
9. Can you create an instance of an `abstract` class? Also, look up the Java keyword `final` and see if you can explain why a class CANNOT be both `abstract` and `final`.
   You can't create an instance of an abstract class. But subclasses of an abstract class can. Because final classes *cannot* have subclasses, if a class were to be final and abstract, it would be impossible to fully implement an abstract class --- the java compiler would probably fail to compile. 
      
10. What happens when a method *overrides* another method? If a parent and child class have methods with the same name, when you call that method on an instance of the child class, which implementation of the method will be executed?
    When you have a method with a certain name that performs a certain operation, and you want to use this method with different return types or parameters? You override it.  for example, maybe I have a method that calculates an average that only takes two integer parameters. I could make a method with the same name that took two double parameters. This would not create a problem with the java compiler. The coolest part is that the compiler/runtime will automagically use the right method, should I call it with two ints or two doubles.

    When a parent and a child have the same name for a method, if the method is called by the child, the child's method will be called first. The parent's method can be called with the super keyboard. 
    

11. What is the relationship between `List`, `LinkedList`, and `ArrayList`? Why do we call a method *polymorphic* if it takes an input of type `List` rather than an input of type `LinkedList` or `Arraylist`, and why is that useful?
    List is a parent to LinkedList and ArrayList. Because certain members are reused/repurpused by overriding, this technical achievment is known as polymorphism... a member variable or method with one name might manipulate data very differently depending on which parent or which child's version is being called. Slightly off topic, but one cool thing about using a parent variable (don't know if this is directly related) is being able to use a reference variable of a parent type to refer to its children. We saw this in class today when we looped an Animal through an ArrayList of animals, and used the same reference variable to tel subclass objects to execute their methods. 

#### Deliverable

This file, with your answers added

## Additional Resources

Refer to the [Classes lesson](https://github.com/ga-adi-nyc/Course-Materials/tree/master/lessons/java-essentials/classes-lesson), the [Subclassing lesson](https://github.com/ga-adi-nyc/Course-Materials/tree/master/lessons/java-essentials/subclasses-lesson), and the [Interfaces & Abstract Classes lesson](https://github.com/ga-adi-nyc/Course-Materials/tree/master/lessons/java-essentials/interfaces-and-abstract-classes-lesson).

Feel free to google these concepts as well. There are plenty of Java tutorial websites and StackOverflow posts that can help you. But be sure to write up your answers in your own words - copying and pasting some text does NOT help you actually learn!
