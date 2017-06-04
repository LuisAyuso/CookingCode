## Control Flow

### Write down the steps, and follow  them one at the time.  

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

Each programming language may have a different definition of statements, but (once again) imperative languages share most of the features:

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

Statements can be grouped into sequences, which will help us to better organize ourselves. Languages like C, C++, Java, JavaScript, Rust... join statements in a group by listing them between curly braces ( *{* and *}* ). On the other hand, Python uses the indentation as groping mechanism, which is somehow controversial by easy to adopt. Nevertheless we will talk about this issue later on.

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

- Forking conditions.
- Loop conditions.

A forking condition enables one path of steps or another depending on a given decision:

_"If the potatoes big, cut them in 4 pieces, otherwise, cut them in half."_

This condition will prepare the cook to handle two possible scenarios. Although we do not know what kind of potatoes he may find in the kitchen, our recipe is ready. With conditions we can prepare the program to evaluate the situation and act. 

#### Calculate the absolute value of an Integer number:
