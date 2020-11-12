# Out of the Tar Pit
## 2. Complexity
- "No Silver bullet" Boorks identified four reasons why building software is hard: Complexity, Conformity, Changeability, Invisibility
- Complexity is the root cause of most problems in large systems.
- Complexity destroys the possibility of a software to be understood.
- Hoare quote: "The price of reliability is the pursuit of the utmost simplicity"
- The unfortunate truth: Simplicity is hard

## 3. Approaches to Understanding
- Two widely-used approaches to understanding systems
  - Testing: understand a system from the outside - as a "black box", observations about how it behaves in certain specific situations.
    - leads to more errors being detected.
    - can be used to show the presence of bugs but never to show their absence.
  - Informal Reasoning: understand the system by examining it from the inside. 
    - leads to less errors being created.
- Because of the limitations of all these approaches, simplicity is vital.

## 4. Causes of Complexity
### Complexity caused by State
#### on testing
- "try it again", "restart the program", "reinstall" ... such recommendations are directly related to the problems that state causes.
- One particular state tells you nothing at all about the behavior of that system in another state.
- Common approach of testing to a stateful system: start from "clean" state.
  - Then assumes that the system would perform the same way in other states
- Things can go wrong when the system happens to be in a "bad state".
- Even though the number of possible inputs may be "very large", the number of possible states can be often "even larger"

#### on informal reasoning
- Mental approaches goes each possible state one by one and the possible states grow exponentially.
- Stateful procedures contaminate other procedures - Even though a procedure is itself stateless, if it make use of stateful procedures, we can only understand the statelss procedure in the context of states.

### Complexity casued by Control
- When control is an implicit part of the language, then the program must be understood in that context.
- Even when programmers want to specify a relationship between certain values, they have been unecessarily forced to choose an arbitrary control flow.
  - It complicates informal reasoning by forcing a reader to duplicate the work of the compiler. Mistakes in this determination can lead to very subtle and hard-to-find bugs
- Concurrency is normally specified explicitly in most languages.
  - Difficulty comes from adding number of possible scenarios in mind.
- Repeated testing is not able to assure the result consistency.

### Complexity caused by Code Volume
- Easiest form of complexity to measure, interacts badly with the otehr causes of complexity.
- Effectively managing two major complexities may achieve linear growing complexity along code volume.

### Other casues of complexity
- duplicated code
- dead code
- unnecessary abstraction
- missed abstraction
- ....
- The more powerful a language, the harder it is to understand systems on it.

## 5. Classical approaches to managing complexity
### object-orientation
- primary strenghs of the OOP: *abstract data type*, *encapsulation*
- Multiple objects constraints are not easily handled.
- Introducing equivelnce relation between objects adds complexity to the task of reasoning.
- Message-passing model of concurrency may help to informal reasoning in some cases.
- Suffer from both state-derived and control-derived complexity.
  
### Functional Programming
- The primary strength of it is that the entire system gains "*referential transparency*" by avoiding state (and side-effects).
- Both informal reasoning and testing become much more effective by avoiding state dependency.
- A mutable state hidden inside is replaced by an extra parameter of both input and output.
- **More generally, whatever the language being used, there are larger benefits to be had from avoiding hidden, implicit, mutable state.**
- The main weakness of functional programming arises when the system must maintain state of some kind.

### Logic Programming
- I have not utilized such a paradigm.. may be *coq* is one example?
- Stating a set of axioms and the attributes required of something to be considered a solution.
- Running the system is equivalent to the construction of a formal proof of each solution.