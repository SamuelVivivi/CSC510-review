________________
# Review Ques 5



1. As precisely as you can (two lines each, at most), define the following.  Your definition should mention inputs,outputs and side-effects:
    - functions

???A function is a block of organized, reusable code that is used to perform a single, related action. No side effect.

    - predictes

Predicate is a function that takes one element as input parameter and return either true or false. Also updates bindings. 

2. Assume a purely logic language where any word starting with upper case is an unbound variable.
   In that logical language what are the outputs and side-effects of the following:
    - emp(tim,42) = emp(Name,Age)
    
    Output : TRUE | Side Effect : Name = tim, Age = 42
    
    - emp(Who,42)  =  emp(tom, Age)
    
    Output : TRUE | Side Effect : Who=tom, Age = 42
    
    - emp(tom,42) = emp(tim,Age)
    
    Output : FALSE | Side Effect Age= 42

3. Closures
    -  Define "closures"?

A useful thing that closures can do is keep track of internal state. A closure is created when:

The scope of some inner function refers to an outer scope's variables.

The inner function is passed around as a variable, carrying with it the inner scope and the outer scope.

    - In the following, when the `add` variable is initialized, what are the two parts of it contents?
    
 An anonymous function, and the variable counter

    - In the following, When the above `add` is created, then used 3 times, what is returns?             
```
 add = (function () {
    var counter = 0;
    return function () {return counter += 1;}
})();

add();
add();
add();
```

 It always returns the anonymous function. If you want to get the counter values, you have to execute the anonymous function. 
For ex : 
Var a = add() // add returns anonymous function
a() // returns 1
a() // returns 2
a() // returns 3

4. Type inference
     - It is claimed that languages that support type inference are less buggy. Why?

They don’t run into type mismatch during Runtime. Those cases are handled during compilation itself. 
     
     - Why might type inference be easier in Python than Java?

Python is a dynamically typed language. Variables are not bound to a type by default. 


5. Folding
     - What is folding?

In functional programming, fold (also termed reduce, accumulate, aggregate, compress, or inject) refers to a family of higher-order functions that analyze a recursive data structure and through use of a given combining operation, recombine the results of recursively processing its constituent parts, building up a return value.

     - What does the following expression return? _foldl (+) 0 [1,2,3,4,5]_

15

6. Erlang
     - Nome one way Erlang is fundamentally different to Python.

Erlang is a functional programming language

     - Describe uses of Erlang in 2 industrial applications. What aspects of those applications lead to the
       use of Erlang?

Whatsapp and telephone switches. It can be up at all time, during the software patching period, if there's a call on the line, it will still be on the line during that period.

Erlang's main strength is support for concurrency. It has a small but powerful set of primitives to create processes and communicate among them.

Erlang provides language-level features for creating and managing processes with the aim of simplifying concurrent programming.


7. Heuristics
     - what is YAGNI? Describe an industrial scenario where YAGNI might save development costs.

"You aren't gonna need it". "Always implement things when you actually need them, never when you just foresee that you need them.

ALGOL is an example of software disasters caused by over-designed systems which were so complicated that nobody was able to implement them properly. YAGNI approach here could have reduced the development scope, and added only essential features in its libraries.


     - what is the rule of 3? Describe an industrial scenario where YAGNI might save development costs.

Rule of three is a code refactoring rule of thumb to decide when a replicated piece of code should be replaced by a new procedure. It states that the code can be copied once, but that when the same code is used three times, it should be extracted into a new procedure.

8. Patterns: Suppose you are working with a 3-tier architecture system for employee management. The system composed of  a database layer, business logic, and GUI. Many parts of codes are reused in this system. As an example: the database needs to know the valid ranges for `age` and so does the GUI.
     - What design pattern might be useful for the  business logic associated with this application? Give reasoning on behalf of your answer.

Bridge.

We decouple an abstraction from its implementation so the two can vary independently. This helps us exert control over the business logic without affecting the GUI or database since the interfaces are now decoupled.
     
