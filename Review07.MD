# Review Ques 7

## Patterns:

1. What is a visitor pattern and why is it useful? 

The visitor design pattern is a way of separating an algorithm from an object structure on which it operates. A practical result of this separation is the ability to add new operations to extant object structures without modifying the structures. 


The nature of the Visitor makes it an ideal pattern to plug into public APIs thus allowing its clients to perform operations on a class using a “visiting” class without having to modify the source.

2. Give an example where factory pattern is suitable in class design. How could factory be usefully combined with visitor.

Define an interface for creating an object, but let subclasses decide which class to instantiate. The Factory method lets a class defer instantiation it uses to subclasses.


3. What is a singleton pattern? Give an example. What is the connection between factory and singleton?

Ensure a class only has one instance and provide a global point of access to it.

4. What is coupling and cohesion among classes? Ideally, how should design alter these values? Justify your answer.

1)Cohesion refers to what the class (or module) will do. Low cohesion would mean that the class does a great variety of actions and is not focused on what it should do. High cohesion would then mean that the class is focused on what it should be doing, i.e. only methods relating to the intention of the class. 2) Coupling refers to how related are two classes / modules and how dependent they are on each other. Being low coupling would mean that changing something major in one class should not affect the other. High coupling would make your code difficult to make changes as well as to maintain it, as classes are coupled closely together, making a change could mean an entire system revamp.

All good software design will go for high cohesion and low coupling.

5. What is the layered patterns? Name one advantage and one disadvantage for layers. 

Components are organized into horizontal layers, each layer performing a specific role within the application 

Layer i is allowed to communicate only with i+1 layer or i-1 layer.

Advantages: Easier to debug, replace on layer with another and check for impact only in plus minus 1 layer.

Disadvantage: Inflexible.



6. What is the proxy pattern? What does it offer to coupling? What does it offer to layers?

A proxy is a class functioning as an interface to something else. The proxy could interface to anything: a network connection, a large object in memory, a file, or some other resource that is expensive or impossible to duplicate.

Proxy patterns generate a loose coupling between the caller and the callee. You can very well vary the callee without worrying about informing the caller.

Proxy patterns naturally fit well in layered architecture since these can be used to communicate between layers simultaneously providing a loose coupling.


7. A body has several limbs. Limbs have extremities (hands or feet).  Extremeties contain toes or fingers. 
   -  Which design pattern is similar to this structure?
Composite pattern


   - Briefly describe the components of that design pattern.
  
This is similar to the composite design pattern.

In this pattern, we Compose objects into tree structures to represent whole-part hierarchies. Composite lets clients treat individual objects and compositions of objects uniformly.

Structure of composite pattern

composite -> leaf or composite

## Anti patterns:

8. What is a god class? How to recognize it? How to fix it?

A "God Class" is an object that controls way too many other objects in the system and has grown beyond all logic to become The Class That Does Everything. 

Recognize:
Class diagram composed of a single complex controller class surrounded by simple data classes.  Single class with a large number of attributes, operations, or both.  A disparate collection of unrelated attributes and operations encapsulated in a single class.  A migrated legacy design that has not been properly refactored into an OO architecture.

The solution involves a form of refactoring. The key here is to move behaviour away from the “God Class”. Identify and categorize related attributes and operations and create different classes for them.

9. For OO purists, "type switching" statements are bad. What is an example of such a statement. How to fix it? What general principle of OO is demonstrated by that fix?

e.g
```
   void speak(){
    switch(type){

        case DOG: println(“woof woof”);
        case CAT: println(“mew”);
        case TIGER: println(“roar!!“);
    }
}
```
Fix:
Create subclasses for each value of the coded type. Then extract the relevant behaviors from the original class to these subclasses. Replace the control flow code with polymorphism.

Polymorphism is demonstarted by this fix.

10. Do all bad smells really matter? Explain.

No. Dr. Tim Menzies argues against this in his paper, Less is More: Minimizing Code Reorganization using XTREE claims the answer to be No.

The premise of this paper is that not every bad smell needs to be fixed.

The paper introduces XTREE, a framework that analyses a historical log of defects seen previously in the code and generates a set of useful code changes. Any bad smell that requires changes outside of that set can be deprioritized (since there is no historical evidence that the bad smell causes any problems).

XTREES recommendations were evaluated and cross-checked using multiple data sets of code metrics and defect counts.

11. Give two examples of each of the following bad smells:
    - Bloating

    Long Method; Large Class; Primitive Obsession; Long Parameter List; Data Clumps 

    - Dispensable

    A dispensable is something pointless and unneeded whose absence would make the code cleaner, more efficient and easier to understand.
    
    Comments; Duplicate Code; Lazy Class; Data Class; Dead Code; Speculative Generality

    - OO abusers

    All these smells are incomplete or incorrect application of object-oriented programming principles.

    Switch Statements; Temporary Field; Refused Bequest; Alternative Classes with Different Interfaces

    
12. Below are a list of OO designs and Arthur Riel's OO  heuristics. Describe how to fix the design so that it agrees with the heuristic:
    - **Design:** One central class has 20 distinct methods for account creation, 60 distinct methods for account auditing, 50 distinct methods for writing objects to a SQL database.   
  **Heuristic 3.3** Beware of classes that have many accessor methods defined in their public interface, many of them imply that related data and behavior are not being kept in one place.



    - **Design:** You need to use a commercial API that highly couples the business logic and GUI layers.  
  **Heuristic 3.5:** In applications which consist of an object-oriented model interacting with a user interface, the model should never be dependent on the interface. The interface should be dependent on the model.




    - **Design:** In your math API, integer class inherits from fractions class.  
  **Heuristic 5.1** Inheritance should only be used to model a specialization hierarchy.
