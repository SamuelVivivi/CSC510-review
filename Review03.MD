# Review Ques 3 02/14/2017

## Requirement Analysis:

1)   Defend the following statements

       - Before building any software, it is wise to spend much time collecting details requirements docs.

Ideally, we look before we leap so that we can find the best ways to do proceed (and we don't get it wrong).
       
      - Requirements engineering is a waste of time

Experience tells you more than excessive initial analysis, recent research says requirements are an illusion.

2)    What is commit partition? What is commit partition strategy in spiral model?

each time we hit that line, it is a commit partition. and here, we STOP if we fail the review criteria


3)    Defend the following statements

        - Reuse is the key to productivity

Economically, there is a major financial incentive to reuse your created, purchased, and acquired assets. 

        - Reuse is dangerous 

beware of accepting deliveries from countries that do not honor your own country's license, patents, innovation, and copyrights. 

        
4)    What are the arguments for and against pushing small codes to review?

Ship small diffs, and stand a snowball’s chance of inspecting them for correctness; because code isn’t correct until it’s running production; because the last thing you changed is probably setting those fires. code review! smaller = faster = more thorough!


Against:  Limiting the amount of code you push is going to block progress, unless you can simultaneously increase the rate of pushing code. This is not as easy as it sounds, and it will shift the focus of your developer tooling budget in the direction of software built with this goal in mind.  You don’t need elaborate Git release rituals. Ceremony such as tagging releases gets to feel like a waste of time once you are releasing many times per day.

______________________________________________
 
  ##Visual Notations for Programming:
 
5)    Write two advantages of state chart. 

Directly translatable to executable code. Many tools from the formal verification community to prove properties across FSMs + WHich is very important for safety critical software. precise semantics. thus enabling automated tool for verification/optimization . also, some claim visual formalisms are superior , instantly accessible etc. yeah, right... when the diagrams get too big, everyone gets confused




6)  When state chart is not recommended?

hard to maintain unless auto-generated from some higher-level spec
hard to scale (all that detail! oh my!)
also, very low-level: hard to get that much information about all systems.
Cannot be used when interfacing to another black-box system you know nothing about
Irrelevant for the mash-up world (no knowledge of internals)


7 )  Draw a state chart for the following states and transitions:
struct transition state_transitions [] = {
{entry, ok, foo},
{entry, fail, end},
{foo, ok, bar},
{foo, fail, end},
{foo, repeat, foo},
{bar, ok, end},
{bar, fail, end},
{bar, repeat, foo}};
  

8) Write three differences between SQL and No-SQL.

SQL databases are table based databases whereas NoSQL databases are document based, key-value pairs, graph databases or wide-column stores. 

SQL databases have predefined schema whereas NoSQL databases have dynamic schema for unstructured data.

SQL databases are vertically scalable whereas the NoSQL databases are horizontally scalable.

SQL databases uses SQL ( structured query language ) for defining and manipulating the data, which is very powerful. In NoSQL database, queries are focused on collection of documents

9)    Suppose you have three tables in database: University, Subject and Student. What are insert, update and delete anomalies in this context?

if data stored in some hierarchical structure (e.g. students inside subjects) then cant INSERT a student unless a subject exists first.; if students in the same structure are stored in multiple subject ddirectories, then if a student changes address it would be posible to UPDATE the student's address in one diretrory but not the others. similairly, it would be possible to delete all students, accidently just by deleting all subjects


10)    How ER based model solves different anomalies for the above scenario? Explain.

solves inconsistency by mapping relations

11)    Why does some people claim ER is not suitable for agile development?

One of the advantage of Agile is that it has the ability to regular adapt changing circumstances, for ER model it's hard to change and harder to scale.
Agile development involves a lot of changes during development stage whereas changes to ER models could be more difficult to change and time consuming

	+ in agile - data is frequently changing
	+ er diagram takes time to build
	+ still have to write implementation code


12)    What state chart and ER based models have in common?

They can be directly implemented into code.

13)    What is compartmental model? Give a small example of using this model for a grocery shop supply chain from warehouse to supermarket shelves.

flows - inflows and outflows of stocks
- representation of first order linear differential equation or derivative
- time is a central driving force
- disadv
	+ time is discrete and fixed, which in all states leads to inaccuracy
	+ hard to know if system is really closed, can be leaky
	+ sensitive to starting configuration - can vary widely
	+ homogeneity assumption - are stocks truly homogeneous
	+ correctness of equations

Departmental store compartmental model
- stocks - grocery products
- inflows - warehouse
- outflows - department
- valve - product transfer rate
- flow enhancer/inhibitor - transport personnels - vehicles - weather - gas prices - cost of transportation - time of transportation

References:
- https://wiki.eclipse.org/Introduction_to_Compartment_Models
- http://www4.ncsu.edu/%7Emsolufse/Compartmentmodels.pdf


14)    What are the limitations of compartmental model?

many (most) programming tasks are time-less. So CM is not applicable to general models.



