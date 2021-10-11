# Review Ques 4

1. What one thing we should be expect in:

       - a poorly architectured system?


       - a well architectured  system?

Something that lets you work alone half the time, team members can be productive in isolation, but know when they need to talk to others.

2. Package switching network (PSN):

       - Define the components of a PSN

Nodes, hosts, packets. psn = package swtich network. nodes edges. data labelled with distination node ids streaming over the edges. if a package arrives at a node that is its distination, it is eaten there. else, it is dispatch owards

       - What other architecture was package switching designed to replace?

Circuit switching

       - Why was an advantage of that other architecture?

dedicated channel for single user. User efficiency.


       - What feature of PSN make it attractive as an alternate architeture?

utilize of resources by all parties. Not charged only by one person.

3. Blackboard architecutures:

       - Define the components of a blackboard architecture;

7a) agents, buzzing around a shared data space.
7b) the shared data space (a.k.a. the blackboard)
7c) agents watch the blackboard, not each other
7d) for advanced pattern recognition applications, the blackboard is divided hierarchically and agents read from layer i to write some high-lelvel knowledge to layer i+1

       - For which projects are  blackboard architectures are ideal?  

 7e) when idealy? trying to co-ordinating large, loosely structured communities.  e.g. gangs of grad students working at different universities on the same goal

4. Pipe and Fiter:
       - Describe the components of a pipe and filter architecture.

a pipeline consists of a chain of processing elements (processes, threads, coroutines, functions, etc.), arranged so that the output of each element is the input of the next; Usually some amount of buffering is provided between consecutive elements. The information that flows in these pipelines is often a stream of records, bytes or bits, and the elements of a pipeline may be called filters.

       -  Give an example of a commonly used system that makes extensive use
         of pipe and filter

Unix

       - Explain one advantage of pipe and filter

Simplicity – Allows designer to understand overall input/output behavior of a system in terms of individual filters.

Concurrent Execution –Each filter can be implemented as a separate task and be executed in parallel with other filters.


       - Explain one disadvantage of pipe and filter

Interactive transformations are difficult – Filters being independent entities designer has to think of each filter as providing a complete transformation of input data to output data.

No filter cooperation.

Performance – may force a lowest common denominator on data transmission

5. Layered architectures:
       - What is "LAMP" and why is it an example of a layered architecture?

LAMP = Linux apache mysql php (python). Segregates functionality into separate segments in much the same way as the layered style, but with each segment being a tier located on a physically separate computer.

       - Explain one advantage of a layered architecture.

Abstraction. Layered architecture abstracts the view of the system as whole while providing enough detail to understand the roles and responsibilities of individual layers and the relationship between them.

       - Explain one disadvantage of pipe and filter

Interactive transformations are difficult – Filters being independent entities designer has to think of each filter as providing a complete transformation of input data to output data.

       - What is "MEAN" and why is it sometimes called a "leaky layered" architecture?

MEAN = MongoDb, Express, Angular, NodeJS. Everything is done in JavaScript, and there's no OS involved.

open for the agile folk to run around and do things like (a) build unified testing frameworks that work at all layers of the system (b) run optimizers across the whole system (c) do anything at all across the whole system. layers aren't meant to be like that. layers are meant to be "you live at layer[i] and you only ever see the api to layer i+1 and i-1

[5:09]  
in LAMP, you can do that "full layered" analysis. you write your (e.g.) php code up HERE and hope the linux OS down THERE work ok.


       - Why is MEAN replacing LAMP in certain fast-paced organizations?
One language (JavaScript), one language up and down the stack (javascript) so (1) faster integrated testing; and (2) faster invention of new patterns.; NoSQL database, easy to scale.


6. CRUD:
       - What is the CRUD pattern?

In computer programming, create, read, update and delete (as an acronym CRUD or possibly a backronym) (Sometimes called SCRUD with an "S" for Search) are the four basic functions of persistent storage.
Sometimes CRUD is expanded with the words retrieve instead of read, modify instead of update, or destroy instead of delete. It is also sometimes used to describe user interface conventions that facilitate viewing, searching, and changing information; often using computer-based forms and reports.

       - Give two example where CRUD pattern is used. 

Databases
Distributed database services
RESTful interfaces


7. In Windows
    machine if you open one folder in two different views, rename folder in
    one view automatically renames the other.
       - What type of architecture is this?  

Subject-Observer

       - Describe different components of this architecture with respect to the above example.

The observer pattern is a software design pattern in which an object, called the subject, maintains a list of its dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their methods.
       
