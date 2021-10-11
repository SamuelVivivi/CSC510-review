# Review 2 : Questions 2/14/2017

## Early lifecycle project planning:


1.    What are drawbacks of early requirement addressing?

premature commitment to the wrong ideas can misdirect a project. advocates of agile claim better to get some experience before fully creating requirements

2.    Define and distinguish unit, system and integration testing.

Unit testing is a software development process in which the smallest testable parts of an application, called units, are individually and independently scrutinized for proper operation.

System Testing is a level of the software testing where a complete and integrated software is tested.

Integration testing, also known as integration and testing (I&T), is a software development process which program units are combined and tested as groups in multiple ways. In this context, a unit is defined as the smallest testable part of an application.

3.    Describe two problems of underestimation effort.

- Schedule and budget overruns
- Loss of quality assurance

4.    Describe two problems of overestimation effort.

- Hinders acceptance of promising ideas
- threatens organizational competitiveness

5.    Boehm reports a certain shape in the cost-estimation uncertainty curve as a project moves from initial planning to final delivery
    - Draw that shape

![boehmEstimation](https://github.com/txt/se17/blob/master/img/boehmEstimation.png)

     - Why does the  shape change as the development continues?

Becuase at first, lack of maturity requires focus on risk and uncertainty issues, which makes it harder to estimate, later on, there are sufficient maturity to support detailed, high fidelity cost and schedule estimates, which makes it more accurate.

6. According to Brook's Law, why does adding more programmers to a late project make that project later?

(1) It takes some time for the people added to a project to become productive. (2) Communication overheads increase as the number of people increases. (3) Limited divisibility of tasks. Adding more people to a highly divisible task such as reaping a field by hand decreases the overall task duration (up to the point where additional workers get in each other's way). 



## Process planning:

0.    Draw the v-diagram. Divide into 

![vmodel](https://github.com/txt/se17/blob/master/img/vmodel.png)

Software =

1/3 planning (requirements, design)
1/6th coding,
1/4 unit test,
1/4 system test


1.    Spiral models
       - What is the commit partition?

each time we hit that review line, it is a commit partition. and here, we STOP if we fail the review criteria

       - How is spriral connected to waterfall?

In the development part of spirial, it uses the waterfall model.

      - How is the spiral model _different_ to waterfall model?

In case of a waterfall model, the stages are in a sequence. Once one stage is over, the process moves to the next phase. Hence, accommodating changes in the middle is difficult. On the other hand, accommodating changes in requirement is easy in a spiral model. This is because we need not start from the beginning because prototypes are created in every phase. Secondly, because of the sequential nature of Waterfall model, if any mistake is done in between of a phase, we may need to begin from scratch. On the other hand, in spiral model because the prototypes are tested at the end of each phase, mistakes can be handled.

      - How is the spiral model _the same_ as the waterfall model?

In the development process of spiral, it contains several waterfall models.

2.    When spiral model should not be practiced? Explain.

Hard to go Spiral if you work for an external software consultants who are struggling for jobs, since any cancellation may be fatal to their plans.

3.    Facebook ships many small changes, very often.
      -  Which kind of s/w strategy method this is? 

Many bangs

4.    What are the phases of Test Driven Development cycle?

RED: Start by thinking of a behavior you want the software to have which could be implemented by a few lines of code (fewer than five is a good target). Then write a test (also only a few lines of code) that will fail unless that behavior is present. 

GREEN: Write just enough code to get the test to pass. 

REFACTOR: Now that the code does what you want, use refactoring to make the design right.


      -  List and explain three advantages of Test Driven Development?

Over-engineering. I have a tendency to "throw in" functionality I "know" I'm "going to need". Making one red test green (along with the list of future tests) helps me implement just enough. I need to find a new way to stay focused.
API feedback. Get quick feedback about my API decisions.

Logic errors. Catches pesky errors.

Documentation. Communicate how I expect APIs to be used and to record what I was thinking during development.

Feeling overwhelmed. With TDD, even if I couldn't imagine an implementation I could almost always figure out how to write a test (finding the next "step up the mountain").

Separate interface from implementation thinking. I have a tendency to pollute API design decisions with implementation speculation. TDD separates the two levels of thinking while still providing rapid feedback between them.

Agreement. A way to be precise with a programming partner about what problem I'm solving.

Anxiety. TDD gives me an instantaneous "Is Everything Okay?" button.

      -  List and explain three disadvantages of Test Driven Development?

Notes that unit tests are very small while function tests (aka system tests) are much larger, much more complex.
Much slower to run, not the kind of thing to give you instant feedback.

"Today however, my team told me the tests are more complex than the actual code."

"Unit tests are unlikely to test more than one trillionth of the functionality of any given method in a reasonable testing cycle. Get over it."

"If you find your testers splitting up functions to support the testing process, you’re destroying your system architecture and code comprehension along with it. Test at a coarser level of granularity."

"Tests should be designed with great care. Business people, rather than programmers, should design most functional tests. Unit tests should be limited to those that can be held up against some “third-party” success criteria."

"If you have a large unit test mass, evaluate the feedback loops in your development process. Integrate code more frequently; reduce the build and integration times; cut the unit tests and go more for integration testing. "


## Effort estimation

1. What is software overestimation? What are its effects on development?

The actual effort to build the software is less than what has been estimated in the beginning.

Overestimation hinders the acceptance of promising ideas, thus threatening organizational competitiveness.

2. What is software underestimation? What are its effects on development?

The actual effort to build the software is more than what has been estimated in the beginning.

Underestimation results in schedule and budget overruns, which may cause project cancellation

3. What is "big bang estimation"? Describe its advantages and disadvantages.

Estimate at the start to allocate resources.

Advantage: Needed when development part of very large resource allocations

Disadvantage: If the scope or technology changes during the period of the project, then the big bang's estimates will be wildly inaccurate.

4. How to do run software projects via "feature maturity"?

Developers compete to get their new feature mature enough to add into existing platform; The "winning" developers are rewarded (financially at annual review time, with promotions) if their features make it in.

     - What kinds of organizations are suitable for adopting this strategy?
     
     Large organizations with an existing product and cash flow work as follows.
     
5. What is parametric software effort estimation?

Collect data on some pre-defined set of values, map it into a pre-defined parametric form.

    - What is needed to use this kind of estimation?
    
    
    
6. Explain each of the following approaches to effort estimation:
     - Big bang?
     
     Make Starting Amount of Money Small; Deliver Working Software Often; Fund a Pilot That Delivers Working Software; Then Use Modeling to Forecast Schedule; Move From Contract Negotiation to Partnership
     
7. An analysts estimates the development time of a softare project, as a single value. What are the drawbacks to such a single-point estimate?

Some degree of uncertainty is inherent in the analysis of real world data. While not all data has performance ranges as large as those seen in above, such ranges are inherent in real-world data. The predictions come from a sampling process and, hence, these conclusions are a distribution rather than a single point.


```python 
_  = None;  Coc2tunings = [[
#              vlow  low   nom   high  vhigh  xhigh   
# scale factors:
'Flex',        5.07, 4.05, 3.04, 2.03, 1.01,     _],[
'Pmat',        7.80, 6.24, 4.68, 3.12, 1.56,     _],[
'Prec',        6.20, 4.96, 3.72, 2.48, 1.24,     _],[
'Resl',        7.07, 5.65, 4.24, 2.83, 1.41,     _],[
'Team',        5.48, 4.38, 3.29, 2.19, 1.01,     _],[

# negative effort multipliers (more means faster)        
'acap',        1.42, 1.19, 1.00, 0.85, 0.71,    _],[
'aexp',        1.22, 1.10, 1.00, 0.88, 0.81,    _],[
'ltex',        1.20, 1.09, 1.00, 0.91, 0.84,    _],[
'pcap',        1.34, 1.15, 1.00, 0.88, 0.76,    _],[ 
'pcon',        1.29, 1.12, 1.00, 0.90, 0.81,    _],[
'plex',        1.19, 1.09, 1.00, 0.91, 0.85,    _],[
'sced',        1.43, 1.14, 1.00, 1.00, 1.00,    _],[ 
'site',        1.22, 1.09, 1.00, 0.93, 0.86, 0.80],[
'tool',        1.17, 1.09, 1.00, 0.90, 0.78,    _],[

# positive effort multipliers (more means slower)
'cplx',        0.73, 0.87, 1.00, 1.17, 1.34, 1.74],[
'data',           _, 0.90, 1.00, 1.14, 1.28,    _],[
'docu',        0.81, 0.91, 1.00, 1.11, 1.23,    _],[
'pvol',           _, 0.87, 1.00, 1.15, 1.30,    _],[
'rely',        0.82, 0.92, 1.00, 1.10, 1.26,    _],[
'ruse',           _, 0.95, 1.00, 1.07, 1.15, 1.24],[ 
'stor',           _,    _, 1.00, 1.05, 1.17, 1.46],[
'time',           _,    _, 1.00, 1.11, 1.29, 1.63]]
```

1.     COCOMO is a parametric effort estimation methods
      - What is the central intuition of the COCOMO equation?

The core intuition behind COCOMO-based estimation is that, as a program grows in size, the development effort grows exponentially.

      - Write down the COCOMO equation (hint: it should fit in half a line)

_Effort = a * KLOC<sup>(b + C/100)</sup> * D_

      - What are the four "P" of the COCOMO attributes? Give one example of each "P"

Platform, personnel, product, process 

note that process is different to product. product is what ur building. process is how you are dong it.

      - In COCOMO co-effecients are shown above, what is `acap` ? What happens to project development effort when it is increased? Why?

Analyst capability. 


      - In COCOMO co-effecients are shown above, what is `cplx` ? What happens to project development effort when it is increased? Why?

Product complexity.

      - From the above parameters, find how much faster a fully distributed system compared to a fully centralized site. If needed, you may assume that the system has 100,000 lines of code.



2.    What is delphi based method?

Use human expertise (possibly augmented with process guidelines, checklists, and data) to generate predictions 
       
       - Why use it instead of COCOMO?

Good for producing one estimate, not a range of estimates.

 there are experts around that know more than any trite simplistic equational model

3.    "Planning poker" is  strategy is suitable for group discussion effort estimation environment
      -  Describe this approach plus one advantage and one disadvantage of using this method.
      
      members of the group make estimates by playing numbered cards face-down to the table, instead of speaking them aloud.
cards were numbered by larger and larger numbers e.g. 0, ½, 1, 2, 3, 5, 8, 13, 20, 40, 100, and optionally a
The cards are revealed, and the estimates are then discussed.
By hiding the figures in this way, the group can avoid the cognitive bias of anchoring, where the first number spoken aloud sets a precedent for subsequent estimates.


Advantage: By hiding the figures in this way, the group can avoid the cognitive bias of anchoring, where the first number spoken aloud sets a precedent for subsequent estimates.

Disadvantage: Estimation changes with different skills and experience

4.    What is no estimate method? When might it be s necessary? 

Just work on projects until they don't make sense, then change gears.

If your organization makes enough money to run itself, and if you view time spent estimating as time not developing, then you might abandon estimates and just write code. 

5.    Case base reasoning is called a non-parametric method.
      - Why? Hint: your answer will have to describe how it works
      
 Case-based reasoning (CBR), broadly construed, is the process of solving new problems based on the solutions of similar past problems. 
      
      - Give 2 advantages and disadvantages of CBR.

Advantage: 
• Can use when have “weak” domain theory
• Reduces knowledge acquisition effort
• Can propose solutions from incomplete problem statement
• Improves over time as case base grows
• High user acceptance
 
Disadvantage： 
• Cases may not cover domain well
• Most appropriate cases may not be retrieved
• Still need similarity, adaptation, and verification knowledge
• In the absence of a good theory, the indexing, retrieval, learning can be ad hoc.


## Requirements

![](http://www.isa.us.es/sites/www.isa.us.es.featuremodelanalysis/files/images/MobilePhone.png)

1.   Consider the above feature model of a mobile phone. What features are allowed and forbidden in this diagram?

Allowed: calls, Screen   Forbidden: Camera without high resolution screen, GPS with basic screen

2.   Consider the design of a car. Every car has a body, transmission, and engine. 
     A car does not necessarily have a trailer. The engine may be powered with gasoline or with electricity or with both. Draw a feature model for car.



2.   A client has asked you to develop a word processor. 
     
     Write two non functional requirements for this scenario. For each, list factors that make them easier or harder to fill
     
Portability : It should work on multiple OS 
Usability : It should be user friendly, with the most used buttons easily accessible 

List two functional requirements For each, list factors that make them easier or harder to fill

Auto correct features 
Export to PDF 




       

