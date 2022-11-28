# CleanCode

##Chapter 1: Clean Code
### There Will Be Code
Code is really the language in which we ultimately express the requirements. We may create languages that are closer to the requirements. We may create tools that help us parse and assemble those requirements into formal structures. But we will never eliminate necessary precision—so there will always be code.

### Bad Code
Bad code slows things down and drags the project into a dead end.

### The Total Cost of Owning a Mess
Every addition or modification to the system requires that the tangles, twists, and knots be “understood” so that more tangles, twists, and knots can be added. Over time the mess becomes so big and so deep and so tall, they can not clean it up. As the mess builds, the productivity of the team continues to decrease, asymptotically approaching zero. 

### We Are Authors
Authors must be able to communicate and understand with their readers. As programmers, we are also authors.
The next time you write a line of code, remember you are an author, writing for readers who will judge your effort.

### The Boy Scout Rule
"Leave the campground cleaner than you found it." Like the rule of scout, we must keep our code clean.
If we all checked in our code a little cleaner than when we checked it out, the code simply could not rot.

## Chapter 2: Meaningful Names
### Use Intention-Revealing Names
Choosing good names takes time but saves more than it takes.
The name of a variable, function, or class, should answer all the big questions. It should tell you why it exists, what it does, and how it is used. If a name requires a comment, then the name does not reveal its intent.

### Avoid Disinformation
Programmers must avoid leaving false clues that obscure the meaning of code. We should avoid words whose entrenched meanings vary from our intended meaning. 

### Make Meaningful Distinctions 
When naming, make sure their functions are well defined, and be mindful of differences in the naming of things that do similar functions.

### Use Pronounceable Names
Programming is a social activity. That's why you should use pronounceable names not abbreviations.

### Use Searchable Names
Searching in code is part of coding. So make it searchable naming.

### Avoid Encodings
Encoded names are seldom pronounceable and are easy to mis-type. Don't use avoid encodings.

### Avoid Mental Mapping
Certainly a loop counter may be named i or j or k (though never l!) if its scope is very small and no other names can conflict with it. Readers shouldn’t have to mentally translate your names into other names they already know. 
 
### Class Names
Classes and objects should have noun or noun phrase names like Customer, WikiPage, Account, and AddressParser. Avoid words like Manager, Processor, Data, or Info in the name of a class. A class name should not be a verb.

### Method Names
Methods should have verb or verb phrase names like postPayment, deletePage, or save. Accessors, mutators, and predicates should be named for their value and prefixed with get, set, and is according to the javabean standard.

### Don’t Be Cute
Choose clarity over entertainment value.
Cuteness in code often appears in the form of colloquialisms or slang. For example, don’t use the name whack() to mean kill().

### Pick One Word per Concept
A consistent lexicon is a great boon to the programmers who must use your code.
Pick one word for one abstract concept and stick with it.

### Don’t Pun
Avoid using the same word for two purposes.

### Use Solution Domain Names
Remember that the people who read your code will be programmers. So go ahead and use computer science (CS) terms, algorithm names, pattern names, math terms, and so forth. 

### Use Problem Domain Names
Use the name from the problem domain. At least the programmer who maintains your code can ask a domain expert what it means.

### Don’t Add Gratuitous Context
Shorter names are generally better than longer ones, so long as they are clear. Add no more context to a name than is necessary.

## Chapter 3: Functions
### Small!
The first rule of functions is that they should be small. The second rule of functions is that they should be smaller than that.

### Do One Thing
Functions should do one thing. They should do it well. They should do it only.

### One Level of Abstraction per Function
In order to make sure our functions are doing “one thing,” we need to make sure that the statements within our function are all at the same level of abstraction. 

### Switch Statements
Unfortunately we can’t always avoid switch statements, but we can make sure that each switch statement is buried in a low-level class and is never repeated.

### Use Descriptive Names
Don’t be afraid to make a name long. A long descriptive name is better than a short enigmatic name. A long descriptive name is better than a long descriptive comment. Use a naming convention that allows multiple words to be easily read in the function names, and then make use of those multiple words to give the function a name that says what it does.

### Function Arguments
The ideal number of arguments for a function is zero. Next comes one, followed closely by two. Three arguments should be avoided where possible. More than three requires very special justification—and then shouldn’t be used anyway.

### Have No Side Effects
Side effects are lies. Your function promises to do one thing, but it also does other hidden things. Sometimes it will make them to the parameters passed into the function or to system globals. In either case they are devious and damaging mistruths that often result in strange temporal couplings and order dependencies.

### Command Query Separation
Functions should either do something or answer something, but not both. Either your function should change the state of an object, or it should return some information about that object. Doing both often leads to confusion.

### Prefer Exceptions to Returning Error Codes
Returning error codes from command functions is a subtle violation of command query separation. It promotes commands being used as expressions in the predicates of if statements.

### Don’t Repeat Yourself 
Duplication may be the root of all evil in software. The duplication is a problem because it bloats the code and will require four-fold modification should the algorithm ever have to change.

### Structured Programming
Every function, and every block within a function, should have one entry and one exit. This rule means that there should only be one return statement in a function, no break or continue statements in a loop, and never, ever, any goto statements.

### How Do You Write Functions Like This?
Massage and refine that code, split out functions, change names, eliminate duplication. Shrink the methods and reorder them. Sometimes break out whole classes, all the while keeping the tests passing.

## Chapter 4: Comments
### Comments Do Not Make Up for Bad Code
Clear and expressive code with few comments is far superior to cluttered and complex code with lots of comments. Rather than spend your time writing the comments that explain the mess you’ve made, spend it cleaning that mess.

### Explain Yourself in Code
There are certainly times when code makes a poor vehicle for explanation. Unfortunately, many programmers have taken this to mean that code is seldom, if ever, a good means for explanation. This is patently false.

### Good Comments
#### Legal Comments
Sometimes our corporate coding standards force us to write certain comments for legal reasons.

#### Informative Comments
It is useful to provide basic information with a comment.

#### Explanation of Intent
Sometimes a comment goes beyond just useful information about the implementation and provides the intent behind a decision.

#### Clarification
Sometimes it is just helpful to translate the meaning of some obscure argument or return value into something that’s readable. Take care that there is no better way, and then take even more care that they are accurate.

#### Warning of Consequences
Sometimes it is useful to warn other programmers about certain consequences. It will prevent some overly eager programmer from using a static initializer in the name of efficiency.

#### TODO Comments
It is sometimes reasonable to leave “To do” notes in the form of //TODO comments.

### Bad Comments
#### Mumbling
Plopping in a comment just because you feel you should or because the process requires it, is a hack. If you decide to write a comment, then spend the time necessary to make sure it is the best comment you can write.

#### Redundant Comments
It’s not more informative than the code. It does not justify the code, or provide intent or rationale. It is not easier to read than the code. Indeed, it is less precise than the code and entices the reader to accept that lack of precision in lieu of true understanding.

#### Misleading Comments
Sometimes, with all the best intentions, a programmer makes a statement in his comments that isn’t precise enough to be accurate. Poor programmer that read misleading comments would find himself in a debugging session trying to figure out why his code executed so slowly.

#### Mandated Comments
It is just plain silly to have a rule that says that every function must have a javadoc, or every variable must have a comment. 


## Chapter 5: Formatting
### The Purpose of Formatting
### Vertical Formatting
### Horizontal Formatting
### Team Rules
### Uncle Bob’s Formatting Rules

## Chapter 6: Objects and Data Structures
### Data Abstraction
### Data/Object Anti-Symmetry
### The Law of Demeter
### Data Transfer Objects

## Chapter 7: Error Handling
### Use Exceptions Rather Than Return Codes
### Write Your Try-Catch-Finally Statement First
### Use Unchecked Exceptions
### Provide Context with Exceptions
### Define Exception Classes in Terms of a Caller’s Needs
### Define the Normal Flow
### Don’t Return Null
### Don’t Pass Null

## Chapter 8: Boundaries
### Using Third-Party Code
### Exploring and Learning Boundaries
### Learning log4j
### Learning Tests Are Better Than Free
### Using Code That Does Not Yet Exist 
### Clean Boundaries

## Chapter 9: Unit Tests
### The Three Laws of TDD
### Keeping Tests Clean
### Clean Tests
### One Assert per Test
### F.I.R.S.T.

## Chapter 10: Classes
### Class Organization
### Classes Should Be Small!
### Organizing for Change

## Chapter 11: Systems
### How Would You Build a City?
### Separate Constructing a System from Using It
### Scaling Up
### Java Proxies
### Pure Java AOP Frameworks
### AspectJ Aspects
### Test Drive the System Architecture
### Optimize Decision Making
### Use Standards Wisely, When They Add Demonstrable Value
### Systems Need Domain-Specific Languages

## Chapter 12: Emergence
### Getting Clean via Emergent Design
### Simple Design Rule 1: Runs All the Tests
### Simple Design Rules 2–4: Refactoring
### No Duplication
### Expressive
### Minimal Classes and Methods
