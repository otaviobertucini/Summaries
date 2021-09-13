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

### Chapter 3

- Functions should be small
    - If statements should have only one line in its body. All the logic above should be inside a function with a descriptive name.
- Functions should do only one thing
    - If a logic of a function can be moved to another function with the name of this new function not just describing the logic behind it, it does more than one thing.
    - For example, if you have a if statement in your function, do not turn it into a function if the name of the new function describes this if statement.
- Try to not mix different levels of abstraction in one function.
    - For example, do not parse a XML in a function that is supposed to generate a set of date. Put the XML parsing inside another function.
    - The code should be read as a story, where each function it contains tells a story about that piece of code. All the particular logic of each part of the story contains its own story.
- Switch cases should be replaced with Abstract Factories.