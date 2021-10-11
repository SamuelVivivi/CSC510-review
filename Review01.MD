# Review Questions 1/19/2017

Test-drven Development

-    According to Kent Beck, why are feedback loops in software development so important?

     It's impossible to write programs right for the first time.

-    When building tests, what is a _mock_ and why are such mocks important?

     + _mock_ is a fake function that mimic the behavior of the real one, so that other functions can run even without the function being declared.

-    What is red green test?

     + **RED:** 
     Start by thinking of a behavior you want the software to have which could be implemented by a few lines of code (fewer thanfive is a good target). Then write a test (also only a few lines of code) that will fail unless that behavior is present. Focus on:
      + The class behavior and its public interface - not how to implement the internals of the class.
      + The class user, not the class implementer - you may need to write the first few tests with class and method names that do not yet exist. Run the test suite, and watch the new test should fail. If the test either does not fail or fails in a different way than you intended, make the necessary fixes.
+ **GREEN:** Write just enough code to get the test to pass. Focus on:
      + Getting something to work
      + Simplest possible implementation, rather than the most elegant solution (even hard-coded values are okay).
      + Reverting to known good code if the test continues to fail
      + If after a few attempts you can't make the test pass, consider starting over with a different test, possibly employing even less code. 

- What are advantages and disadvantages of test-driven development?

### Advantage

+ Over-engineering. I have a tendency to "throw in" functionality I "know" I'm "going to need". Making one red test green (along with the list of future tests) helps me implement just enough. I need to find a new way to stay focused.
+ API feedback. Get quick feedback about my API decisions.
+ Logic errors. Catches pesky errors.
+ Documentation. Communicate how I expect APIs to be used and to record what I was thinking during development.
+ Feeling overwhelmed. With TDD, even if I couldn't imagine an implementation I could almost always figure out how to write a test (finding the next "step up the mountain").
+ Separate interface from implementation thinking. I have a tendency to pollute API design decisions with implementation speculation. TDD separates the two levels of thinking while still providing rapid feedback between them.
+ Agreement. A way to be precise with a programming partner about what problem I'm solving.
+ Anxiety. TDD gives me an instantaneous "Is Everything Okay?" button.


### Disadvantages

   + Notes that _unit tests_ are very small while _function tests_ (aka _system tests_) are much larger, much more complex.
   + Much slower to run, not the kind of thing to give you instant feedback.
   + "Tests might be more complex than the actual code."
   + "Unit tests are unlikely to test more than one
      trillionth of the functionality of any given method in a
       reasonable testing cycle. Get over it."
   + "If you find your testers splitting up
      functions to support the testing process,
      you’re destroying your system architecture and
      code comprehension along with it. **Test at a coarser level of granularity.**"
   + "Tests should be designed with great care. Business
      people, rather than programmers, should design most
       functional tests. Unit tests should be limited to those that
       can be held up against some “third-party” success criteria."
   + "If you have a large unit test mass, evaluate the feedback
      loops in your development process. Integrate code more
      frequently; reduce the build and integration times; cut the
      unit tests and go more for integration testing. "

Process models

- Describe the four parts of the v-diagrams?

    + Planning, coding, unit test and system test.

     - Which part(s) of the v-diagram takes most time?

     +  Planning

     - Which part(s) take least time?

     +  Coding

- Name, in order, at least four stages of waterfall model? 

    + Plan-->Requirement-->Develop-->Test-->Deploy-->Operate

     -  Why is it called waterfall model?

     + It's a downstream serial process.

- Give an example application where the waterfall model might be suitable for. 

    +  Project is short, or the product definition is very stable.

- What are the  major disadvantages of the waterfall model?

    + Once an application is in the testing stage, it is very difficult to go back and change something that was not well-thought out in the concept stage.
    + No working software is produced until late during the life cycle.
    + High amounts of risk and uncertainty.
    + Not a good model for complex and object-oriented projects.
    + Poor model for long and ongoing projects.
    + Not suitable for the projects where requirements are at a moderate to high risk of changing.


- Describe the agile model. 
     - What are its key differences compared to waterfall model?

       Decompose development into multiple short sprints (Plan, design, develop, test)
       
       Less up-front planning, less up-front design
       
       More testing as part of the development, less reliance on downstream testing
       
       Catch problems earlier, avoid downstream rework
       
       Get and respond to feedback earlier, deliver the right thing faster.

     - What are some potential disadvantages of agile?

       In case of some software deliverables, especially the large ones, it's difficult to assess
        the effort required at the beginning of the software development life cycle.
     
     There's a lack of emphisis on necessary designing and documenting.
     
     The project can easily get taken off track if the customer representative is not clear what final outcome that they want.
     
     Only senior programmers are capable of taking the kind of decisions required during the development process.
        Hence it can be harder for newbies to be agile, unless combined with experienced resources.

- Describe  DevOps? Why it is called DevOps?
     
     Development and bussiness do continuous planning using backlog.
     
     Continously conduct design experiments (A/B testing, dark features, etc.)
     
     Development does continously integration and continously testing.
     
     Enable automation of testing and everything else by putting APIs on everything.
     
     DevOps: Improve collaboration between Dev and Ops.
     
     Make support easier -- monitoring, problem determination, etc.

     It's called DevOps becuase operation phase in integrated into development.


Surveys

-    An individual in a survey has three rights.  In 2 lines (each) describe two survey procedures: one that maintains and one that violates
     -   a subject’s right not to participate.
     -   a subject’s right to privacy.
     -   a subject’s right to be forgotten.
-    For each of the following, use 2-5 lines to define and describe:
     -  Semi-structured or structured interviews
          +  Measuring the causal influence of an independent variable by keeping all other independent variables constant via repetition, randomized assignment and averaging.

     -  Questionaires
          +  Collecting information from many responders using a questionnaire

     -  Focus groups
          +  Small pool of participants give feedback on prepared material (e.g. paper prototype)  

     -  Think aloud
          +  Participant vocalizes thought processes during study.

     -  Data analysis (using data mining)
          +  Qualitative data analysis that generates (as opposed to test) theory by abduction, constant comparison, and theoretical sampling.  

-    Pick any two of the above survery methods and describe how one can be **better** than the other.

Think aloud is better than in structured interviews because you gain insight from creative thought from the interviewees.

Questionnaires are better than Semi Structured Interview because they provide a better evaluation of a LARGE group of responses with less effort

-    Pick any two of the above survey methods and describe one can be **worse** than the other.




Stakeholders

-   Who are stake holders?

A stakeholder in the architecture of a system is an individual, team, organization, or classes thereof, having an interest in the realization of the system.


-   What is non functional requirement of stakeholders?

Time (Transactions/sec; Response time;Time to complete an operation)

Space (Main memory; Auxiliary memory; Cache)

Usability (Training time; Number of choices; Mouse clicks)

Reliability (Mean time of failure; Downtime probability; Failure rate; Availability)

Robustness (Time to recover; % of incidents leading to catastrophic failure; Odds data corruption after failure)

Portability ( % of non-protable code; Runs on N operating systems; Runs on desktop, tablet, mobile)

-   Assume you are assigned to develop a website of CSC department. Describe different solution for different stakeholders.



-   What is feature option? Assume you have to design the architecture of a mobile phone. What will be the feature options in this context?

Feature option is what you will build. 
https://docs.google.com/presentation/d/1jXCpyZX_V7rcnxaN5VSrsUKLhF77ZICrYXB2YU5c3Cc/pub?start=false&loop=false&delayms=3000&slide=id.g1b6c823877_2_81

