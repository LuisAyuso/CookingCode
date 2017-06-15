## Control Flow

### Write down the steps, then follow them one at the time.  

So far we have learned how to execute arithmetic operations and somehow tailor them into an arbitrary complex equation. This could be pretty useful but so far we are very little flexible regarding options, repetitions and unexpected scenarios.

Let's draft a new recipe:

#### How to cook potatoes:

- Wash potatoes
- Cut potatoes in half
- Salt half potatoes
- Heat up oven 180ºC
- Cook for 25-30 minutes. Depending on size. Check till skin becomes wrinkled.
- Serve.

First of all, I would like to acknowledge the steps enumeration. Those steps provide a temporal hint to us, and settles an order which will lead to success. Nevertheless is not the only order we can follow, as we can start heating up the oven as step 2, and then cut and salt the potatoes any time between 2 and 5. The rule of thumb here is to write something that can do the job, and we will optimize and improve the code once it is working.

Although we will not pay much attention to the order variations, it is important to notice the steps as individual steps. It does not matter if we can heat up the oven while we cut the potatoes. Those are two separated steps and we will try to avoid interference, otherwise we will end up turning the oven on while we hold a potato in one hand and a knife in the other.

In the same fashion, the code is separated in independent and self contained steps which allow us to reason about the whole procedure. These steps are the next level in programming building blocks and are called statements.

Each programming language may have a different definition of statements, but (once again) imperative languages share most of their features:

#### C, C++, Java
```C
int a = 1;
// this is one line comment
a = a + 1 + 12 + a * 3;
a + 1;
```
#### Python
``` Python
# this is a line comment 
a = 1
a = a + 1 + 12 + a * 3
a + 1
``` 
Every expression is an statement on its own, no matter how complex turns to be. The end is marked by an end of statement token, which in case of C, C++, Java, JavaScript, Rust and others is a semi-colon ( *;* ) character, while other languages like Python use the end of line. The end of line is an invisible character that text software use to mark where a line ends and a new one begins. In other words, In Python we write one statement per line while in the _C, C++, Java, Javascript and Rust _we are allowed to write more than one (still though I may have something to say about this in the style section).

Statements can be grouped into sequences, which will help us to better organize ourselves. Languages like C, C++, Java, JavaScript, or Rust group statements by listing them between curly braces ( *{* and *}* ). On the other hand, Python uses the indentation as groping mechanism, which is somehow controversial by easy to adopt. Nevertheless we will talk about this issue later on.

#### Rust
``` rust
{ 
    let x = 1;
    x + 1;
}
```

### I do what I want. Control flow.

Now that we are able to describe steps, is time to address the second and main new issue in the current recipe:

_"Cook for 25-30 mins. Depending on size. Check till skin becomes wrinkled"_

How can we do this? So far we are only able to execute one operation after another. To be able to break a series of statements and switch to other series of statements we need a common feature of imperative languages: control flow.

Our cook is cooking following the instructions and begins to cook the potatoes in the oven.

1. He opens the oven and lays the potatoes inside.
2. He closes the oven.
3. He waits some time.
4. He opens the oven.
5. He checks if the skin looks wrinkled: If it does not, he goes back to point 2. Otherwise continues with 6
6. Takes the potatoes out of the oven.

Step 5 is slightly more complicated than other steps we have seen before. This is because it is a conditional statement.

There are many flavors in conditional statements and some languages may provide even more, nevertheless there are only 2 significant groups:

- Forking conditions let us choose between options, depending on the condition.
- Loop conditions let us repeat a series of steps, depending on the condition.

#### Forking Conditions

A forking condition enables one path of steps or another depending on a given decision:

_"If the potatoes are big: cut them in 4 pieces. Otherwise, cut them in half."_

This condition will prepare the cook to handle two possible scenarios. Although we do not know what kind of potatoes he may find in the kitchen, our recipe is ready. With conditions we can prepare the program to evaluate the situation and act. 

#### Calculate the absolute value of an Integer number:

The absolute value of an integer value is the value of the digits without the sign. This means that the absolute value of 1 is 1 while the absolute value of -1 is 1.

#### C
``` C
if (x > 0)
{
    x = x
}
else
{
   x = -x;
} 
```

#### Python
```Python
if x > 0:
    x = x
else:
    x = -x
```

Branching conditions drive our code execution and are our first tool to write generic programs: A generic program will let us solve a problem where the input may be different from one execution to another. In other words, branching makes our programs useful. 

There is a second kind of branch which is worth mention because it is implemented in most of imperative languages. The multiple branching condition:

#### Multiple Branch: select an option 

Let's consider the following recipe:

*If our vegetables are green beans: cook them 5 minutes, if they are potatoes cook them 15 minutes, but if they are carrots: cook them 10 minutes*

We could consider to write our code in the following manner:

``` 
    if Vegies are green beans then:
        cook Vegies for 5 minutes
    otherwise:
        if Vegies are potatoes then:
            cook Vegies for 15 minutes
        otherwise:
            if Vegies are carrots then:
                cook Vegies for 10 minutes
```

Although this code is correct, it is somehow cumbersome.  We could forget to indent correctly the code and in this case it would be pretty complicated to follow up. We could need to add many cases and our code will grow towards the right of the screen, eventually requiring us to buy a second display. Even when having a multi display setup can be neat in many scenarios, our left screen will be solely used to print spaces, which is not a very efficient use of our resources.

Let's try to compact this:

``` 
    if Vegies are any of the following: 
        Green beans, then: 
            cook Vegies for 5 minutes
        Potatoes, then: 
            cook Vegies for 15 minutes
        Carrots, then: 
            cook Vegies for 10 minutes
```

The code we wrote is now more compact, nevertheless it provides us with the same instructions to proceed with our recipe. In some programming languages this looks like:

#### C and C++
``` C 
    switch(vegies) {
        case green_beans: 
            cook(vegies, 5);
            break;
        case potatoes: 
            cook(vegies, 15);
            break;
        case carrots: 
            cook(vegies, 10);
            break;
    }
```

TODO: java? pascal? python has not: make a note

#### Repeat after me: Loop Conditions

More than often we will want to repeat some steps to finish a task. An example is pealing potatoes:

#### PseudoCook
``` 
    While there are potatoes in the pot:
        take one potato from the pot.
        peel potato
        drop potatoe in the sink
```

This will then look like:

#### Python
```  python
    while not pot.empty():
        potatoe = pot.pop()
        peel(potatoe)
        sink.append(potatoe)
```

The use of this conditional branches is natural and easy to understand. Nevertheless there are some considerations to keep in mind: We may want to repeat an action as long as a condition is satisfied, or we may want to do something first and repeat until a condition is satisfied. There is a third kind of loop that will simplify most of our code: the for each loop. This kind of loop will allow us to execute some code for every element inside of a collection, whenever this element is a vegetable in a pot, a dish in the sink or an integer number in a list of numbers.

| kind of loop | what does it mean | 
|:------------:|:-----------------:|
| While | Repeat a task while the condition is satisfied | 
| Until | Do a task, and repeat if a condition is **not** satisfied | 
| For each | execute task for each element inside of a collection | 
| Infinite loop | Just like that, loop forever. Forever ever... or maybe not, as we will see later | 

Loops have some properties which let us convert them into other kind of loops. 

* If the condition for a  *while* loop is not satisfied from a beginning, the loop task will not be executed.
* If we know how to evaluate the condition of an *until* loop up front, we can write such as a *while* loop using the negated condition. 
* If we can enumerate the elements in a collection, we can loop throw the natural numbers from 0 to the collection size, then use the current index to access the element: 

*I have 4 apples in the basket: pick up the first apple ..., then pick up the seconnd one...*

When to use each kind of loop can be confusing: each loop can be expressed somehow using another kind. Even so, the art of choosing the right tool is the path to clean code easy to understand, which is good performing as well.

#### While Loop in C
``` C
    // compute the factoral of 10
    int x = 10;
    int result = 1;
    While (x < 0) {
        result = result * x;
        x = x-1;
    }
``` 
#### Until Loop in C
``` C
    // compute the factoral of 10
    int x = 10;
    int result = 1;
    do {
        result = result * x;
        x = x-1;
    }
    While (x > 0); // notice the semicolon after while, this is important!
``` 
#### For Each Loop in C
``` C
    // compute the factoral of 10
    int result = 1;
    for (int x = 10; x > 0; ++x){
        result = result * x;
        x = x-1;
    }
``` 
#### For Each Loop in Python
``` C
    # compute the factoral of 10
    result = 1;
    for x in range(10, 1):
        result = result * x;
``` 

### Break the flow

So far we have enough tools to automatize almost any process. Internally, computers do not have much more instructions than what we have seen until now. Unfortunately we live in an imperfect world and out program may have to deal with all kind of undesired scenarios. Most of the time you spend programming you may be thinking on what else could be happening or how to handle certain scenarios, and you may end up writing complicated chains and waterfalls of conditions to do the right thing every time. To improve the code quality we have some rules, than may let us break the rules:

#### PseudoCook
```
    for each onion in the basket:
        if the onion is not too small:
            wash the onion
            peal the onion
            if the onion is still fresh:
                Chop the onion
                put the chooped onion in the pot
            else:
                throw away the onion
```
As we had 3 kilos of onions, now we had 3 kilos of chopped onions (minus a tinny little bit that got wasted in the way, and 3 onions that were no longer fresh).  This is now way to much onion for my pot, lets try to optimize our onion consumption here:

```
    while pot not full:
        while onions in basket:
            if the onion is not too small:
                wash the onion
                peal the onion
                if the onion is still fresh:
                    Chop the onion
                    put the chooped onion in the pot
                else:
                    throw away the onion
```
After looking at this code we will realize that we will chop all the onions again, just to find out that we messed it up again. Lets try one more time:
```
    while pot not full and onions in basket:
        if the onion is not too small:
            wash the onion
            peal the onion
            if the onion is still fresh:
                Chop the onion
                put the chooped onion in the pot
            else:
                throw away the onion
```
Ok, I this looks like right already. Although this code is correct, we may want to simplify the whole thing a little bit:
```
    for each onion in basket:
        if the pot is full:
            We are done, ignore the rest.

        if the onion is too small:
           ignore the rest, continue with the loop
        
        wash the onion
        peal the onion

        if the onion is not fresh:
           throw away the onion
           ignore the rest, continue with the loop

        Chop the onion
        put the chooped onion in the pot
```

This technique is called *early bail out* and it will make our code more readable because of two reasons:
* It simplifies the conditions, we ask one thing at the time this allows us humans to better think our moves.
* It reduces the amount of nesting conditional branches, we will reduce the amount of *loops* and *ifs* that we nest inside of each other, which makes the code much easier to read.

Said that, those are the magic keywords that will let us break the flow as we please:

| Statement | What it does | Where to use it |
|:---------:|:------------:|:---------------:|
| Break     | it breaks the current loop and exits, it ignores if conditions and breaks the first loop found upwards | When inside of a loop, but we have already completed the whole loop task. When we have more onions but the pot is full |
| Continue | it breaks the task for the current iteration, but it continues with the next | When we do not want to consider this one iteration but we need to continue: The onion is just to small, we move to the next |
| Return | This statement breaks the current function and any loop in it, no matter how many nested loops we have | We will talk about this in the next chapter |
| Program exit | Kill our program | Every programming language has some means to blow up the whole thing in a controlled manner. Sometimes is just the easier way |


### Summary

- Control flow statements
    - Conditional Branches
        - Simple:  ```if``` / ```if else```
        - Multiple
    - Loop
        - While
        - Until
        - For each
        - infinite
    - Break flow
        - Break
        - Continue
        - Return
        - Program exit

### Exercises
