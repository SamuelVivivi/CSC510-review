# Review Ques 6

1.    What are independent testable features? Give example from a multifunction calculator.

Independent testable features are the smallest testable feature that is identified from functional specification. Root calculation is a independent testable feature


2.    Define random testing? What are its advarnages and disadvantes;

Random testing is a black-box software testing technique where programs are tested by generating random, independent inputs. Results of the output are compared against software specifications to verify that the test output is pass or fail.

Pick possible input uniformly, avoid designer bias, treats all input as equally valuable.

Defects are not distributed uniformly. Random sampling are unlikely to cover cases that will make the software goes wrong.


3.    Define and distinguish whitebox test vs blackbox (aka functional) testing?

White Box Testing is a software testing method in which the internal structure/ design/ implementation of the item being tested is known to the tester. The tester chooses inputs to exercise paths through the code and determines the appropriate outputs. White box testing is testing beyond the user interface and into the nitty-gritty of a system.

Black Box Testing is a software testing method in which the internal structure/ design/ implementation of the item being tested is not known to the tester. These tests can be functional or non-functional, though usually functional.


4.    For each of the above
           - list one advantage and disadvantage.

Whitebox advantage: 1)Testing can be commenced at an earlier stage. 2)One need not wait for the GUI to be available.
Testing is more thorough, with the possibility of covering most paths.

Whitebox disadvantage: 1)Since tests can be very complex, highly skilled resources are required, with thorough knowledge of programming and implementation. 2)Test script maintenance can be a burden if the implementation changes too frequently. 3)Since this method of testing is closely tied with the application being testing, tools to cater to every kind of implementation/platform may not be readily available.

Blackbox advantage: 1)Tests are done from a user’s point of view and will help in exposing discrepancies in the specifications. 2) Tester need not know programming languages or how the software has been implemented. 3)Tests can be conducted by a body independent from the developers, allowing for an objective perspective and the avoidance of developer-bias. 4)Test cases can be designed as soon as the specifications are complete.

Blackbox disadvantage: 1)Only a small number of possible inputs can be tested and many program paths will be left untested. 2)Without clear specifications, which is the situation in many projects, test cases will be difficult to design. 3)Tests can be redundant if the software designer/ developer has already run a test case. 4) Ever wondered why a soothsayer closes the eyes when foretelling events? So is almost the case in Black Box Testing.


           - list one circumstance where,  absolutely, you would use and one and not the other

Testing API calls, I would use blackbox over whitebox.

5.    Describe three ways to reduce the effort associated with blackbox testing (by the way: one of them may sound
      a little whitebox-ish).

1)Systematic Partition Testing - Try to split up the Input space into classes, using equivalence partitioning, or boundary analysis. 

2)Condition Coverage - Use heuristics like Pairwise testing, All Pairs testing to cover the input space. 

3)Model Based - Use model and representative values to generate test cases. (Finite State Machines, or Decision Structures) 


6.    A particular kind of white box testing is model based testing
       - Describe model-based testing

Model-based testing is an application of model-based design for designing and optionally also executing artifacts to perform software testing or system testing. Model typically come as finite state machines and decision structures.


       - List two coverage methods fot state-based models.

1) Transition Coverage 2) Condition Coverage


       - Using an example, describe how model-based testing might reduce, significantly reducing the effort of testing.



7.    All pairs testing
        - Describe it (this answer may repeat part of a previous answer)

All pairs testing is a combinatorial method of software testing that for each pair of input parameters to a system, tests all possbile discrete combination of those parameters.

        - Comment: all pairs testing is crazy

It does not cover all the possible test cases.  Number of test cases in all pairs is drastically less compared to the actual number of possible combinations

        - Comment: all pairs testing relies on a realistic assumption about the world.

In the real world, it is hard to reproduce a scenario with more than 2 specific feature values. It is impossible to test everything! 

8.    What is Gunes Koru's heuristic for detecting bugs by inspecting less code? Try to justify why the Koru method might work.

Smaller methods have disproportionately more methods than larger methods.
Sort code smallest to largest; Until you run out of time, read in that order.

According to the paper, smaller modules tend to have higher coupling, and dependency with other parts of code, resulting in higher probability of bugs. 

9.    LOC vs state coverage test: 
         - define LOC coverage

LOC coverage is a measure used to describe the degree to which the source code of a program is executed when a particular test suite runs

         - make an argument that one method might be more efficient than the other?

State covertage is the minimum testing criterion which might not cover the transition where a bug might occur.

State coverage seems more efficient since in a thousands of lines of source code, it becomes extremely difficult to create tests to covery every line. Instead if we create the finite state machine of the system (e.g consider the code of TCP protocol) and create tests to cover every state, thats far more easier, faster and efficient since it correctly encapsulates the working of the system.

10.   Test case prioritization:
         - What are the 20:80 rule for testing? How to use that to optimize testing effort?

80% of software quality is maintained by 20% of programmers;
80% of bugs in an application are written by 20% of developers;
80% of bugs are fixed in 20% of time;
20% of a business application accounts for 80% of bugs;



         - Why not just write tests for everything and run those tests all the time some change is made to the code?

Takes too much time
       
       - List Google's three criteria for priotiziation test cases

1.Always test new features
2. Test feature which has not been tested for a long time
3. Test features which failed recently.

11. Define all-pairs testing.
         - A program has five boolean inputs. A test suite is proposed where 1=false 2=true 0=dontcare. 
	   Do the follow tests satisfy the all-pairs requirement?

```
((2 2 1 1 1)
(2 1 2 2 2)
(1 2 2 1 2)
(1 1 1 2 1)
(0 2 2 2 2)
(0 1 1 1 2))
```


all-pairs testing or pairwise testing is a combinatorial method of software testing that, for each pair of input parameters to a system (typically, a software algorithm), tests all possible discrete combinations of those parameters. Using carefully chosen test vectors, this can be done much faster than an exhaustive search of all combinations of all parameters, by "parallelizing" the tests of parameter pairs.
NO! For the feature pair (3,5), input option (2,1) is missing in the test cases


