# Clean Code

## Chapter 1

- We'll never get rid of code
    - Code is the implementation of the details of an abstraction / concept / requirement
    - The level of detail needed in a requirement can never be too abstracted
- Probably a team that is moving fast is going to lose quality over time because of the bad code created by the rush
- It's the programmer job to defend the good quality of the code against their enemies (CEO, tight schedule, changing requirements)
    - It's like a doctor receiving an order by a patient to not wash his hands before surgery. Clearly the patient is the boss, but the doctor cannot accept such a request.
- A bad code is like a building with broken windows: it looks like people does not care about it. So other people will not care and more windows will be broken.
- Good code = focused code. A good code does one thing well.
- Good code = other programmers can understand and enhance it.
- Good code = code with expressiveness
- Good code = code without duplications
- We read more than write code.
- Keep the code cleaner than you found it

## Chapter 2

- If a variable name (or any other name) requires a comment explaining it, you better change that name
- Try not to use words with different meaning for programmers. documents > documentList
- Try to use names that can be easily spotted and very different of other names.
- Don't use words just for the sake of not repeating an existing variable.
    - For example, do not change a variable *code* to *theCode* just because the first one already exists.
    - And do not use words that means nothing. For example, the classes *Vehicle, VehicleData* and *VehicleInfo* can mean the same thing for a person that never saw the code.
- Use pronounceable names. *documentDate > docDt.*
- Use searchable name for variables or constants.
- Class names should be a noun.
- Methods names should contain a verb.
- Pick one word for function or concept inside the code base. *get, fetch* and *retrieve* all mean the same thing. Choose one and stick to them.
- The bigger the scope, the bigger the name of the variable
    - For global variables, long names such as NORMAL_DOCUMENT_TYPE
    - For small scope variables, small name. An index of a for loop should not have a long name like elementIndex.

## Chapter 3

- Functions should be small
    - If statements should have only one line in its body. All the logic above should be inside a function with a descriptive name.
- Functions should do only one thing
    - If a logic of a function can be moved to another function with the name of this new function not just describing the logic behind it, it does more than one thing.
    - For example, if you have a if statement in your function, do not turn it into a function if the name of the new function describes this if statement.
- Try to not mix different levels of abstraction in one function.
    - For example, do not parse a XML in a function that is supposed to generate a set of date. Put the XML parsing inside another function.
    - The code should be read as a story, where each function it contains tells a story about that piece of code. All the particular logic of each part of the story contains its own story.
- Switch cases should be replaced with Abstract Factories.
- Function with one argument should be those who transforms the argument or answer some question about that argument. Any function different than that should have no arguments.
- Flag arguments should not exist. They say loudly that the function is doing more than one thing. You should split the functions in one for each flag.
- To reduce the number of arguments, we can write a new method for a argument that receives the other as an argument, we can make one argument the property of the class, we can turn the function into a class and pass one argument as the constructor.
- When two or more arguments are needed for a function, the best thing to do is create a class that takes this two parameters as constructor arguments.
    - Example: *generateData(number number, number digit)* turns into *generateData(Key key).*
- Do not create functions that do something and answer something, like:
    - *boolean createUser(username)*
    - This function creates an user and tell if the creation worked.
    

## Chapter 4

- Comments are used to compensate bad code. They should never (or rarely) appear in good code.
- It's better to spend energy in writing good code than to write and maintain comments.
- Comments that make you go to another part of the code to understand it should be removed, because they do not accomplish their goal.

## Chapter 6

- Classes have to hide the implementation of the data it uses.
    - That's why getters and setters are not a good idea.
    - A function between variables is not a abstraction
- It's not recommended that classes call other methods than:
    - From classes that are instanciated in their methods
    - From classes that are passed as an argument
    - From classes thar are instanciated in the class
- This is called Law of Demeter and basically says that a class should only interact with it's friends
    - When we are walking our dog, we do not control it's legs. But instead we orientate the dog through the leach and it moves its legs in response.

## Chapter 7

- Exceptions should provide enough information for the developer to know WHERE and WHY the error ocurred
- Don't return null from functions.
    - It's better to throw an exception or return a special object
    - Null returns need to be treated in the application. What if we miss one of the treatments?
- Another thing is not pass null as an argument

## Chapter 8

- Don't use native types all over the code.
    - Let's say we have an **array** of documents. Because it is an array we can do anything with it (delete, add, etc...)
- We should encapsulate this array in a class Documents, that handles all the interactions with the documents
- Making this, we prevent the programmer of doing something he does not want to
- We also make the code cleaner, because now we can describe (via methods name) what we intend to do
- One good way to learn new libraries APIs is doing learning testes
    - It consists in write little chunks of code to learn the core features of the library and to know how it works

## Chapter 9

## Chapter 10

- It's hard to have a good reason to have public variables
- Classes should be small
    - We measure a class size by the number of responsibilities it has
    - If we can not find a proper name to a class, it is likely that the class is too big
    - Another good hint: if we cannot describe a class without the use of "and", "if" or "or", it is probably big.
- We want the code to look like a toolbox divided into many little labeled compartments, not a big box with everything tossed inside.
- The methods in a class should use the maximum number of its variables.
    - If some variables are only used by few methods, this is a good indicator that there is a new class trying telling you to be created.
- In a cohesive system, we implement features by extending the system, not by changing the existing behevior

## Chapter 12

- Writing good tests implicate in good designs
    - This is true because writing good tests (tests that really verifies if the system works) need a decoupled and cohesive system. It is much easier to test small parts of code that do only one thing

[https://stackoverflow.com/questions/2668355/how-much-abstraction-is-too-much](https://stackoverflow.com/questions/2668355/how-much-abstraction-is-too-much)

## Chapter 16

- Constants in Abstract class ⇒ wrong level of abstraction
- Problem: DayDate uses a SpreadsheatDate (who is based on DayDate)
- Move variables the closest you can from the using class
    - Take them out of the base class and move them down
- Use enum whenever possible
    - Easy to change later
    - Describes a behavior / naming of common things

## Chapter 17 - Heuristics

### Comments

- Inappropriate information
    - Information that was not supposed to be on the code
    - Editing history, PRs tracking, authors
- Obsolete comment
    - A comment that is not in the right place anymore
    - Or the code it was describing was moved or the code changed and the comment not updated
    - Example: a comment telling what dates formats a function accepts
- Redundant comment
    - A comment that just states what the line of code said itself
        
        ```jsx
        // Sums b with c and store in a
        const a = b + c
        ```
        

### Environment

- Tests require more than one step
    - Tests should be easy to execute
    - One click button or one command line

### Functions

- Too many arguments
    - No function should have more than three arguments
    - No argument is best
        - We can do this by using classes
- Output arguments
    - Functions should always return the result, not assign it to a param
- Flag arguments
    - They say that the function is doing more than one thing

### General

- Obvious behavior is unimplemented
    - We cannot lose trust in the person who wrote the code
    - A function should behave according to its name
    - A function called *fetchUsers* should return a list of users, not a single user or null
    - Principle of least surprise
        - If a system is designed to behave in some way, it must behave this way
        - If a system has a high astonishment rate, it should be redesigned
        - Minimize the learning curve
        - 
- Incorrect behavior at the boundaries
    - Test the boundaries cases
- Overriden safaties
    - When we ignore some signals of danger
    - Warnings of the compiler, tests that are not passing