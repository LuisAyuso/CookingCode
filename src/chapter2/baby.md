# Baby steps:
In this chapter we will start programming real computers, using as an example some common languages.

## The beginning: Boring maths.
Computer machines are designed to work on a set of basic mathematical operations because maths can be very useful. Beyond computing complicated mathematical formulas, simple maths provide us with the basic programming building blocks: Basic arithmetic to count things and basic logic to evaluate scenarios. We will use this basic building blocks to build equations that can be evaluated during the program execution.

The following snippets show some basic operations in different languages:

#### C and C++:
```c
1 + 10
true || false
true && true
1.0 * 2.0
```
#### Python:
```python
1 + 10
True or False
True and True
1.0 * 2.0
```
#### Java:
```Java
1 + 10
true || false
true && true
1.0 * 2.0
```

The snippets presented describe all the same 4 operations:

- **1** (value one) **+** (plus, addition) **10** (value ten), which should result in a value **!1** once executed.
- **true** (value **true** or yes) or (the logical distinction) false (value false or not), which result would be **true**
- **true** (value true or yes) and (the logical conjunction) **true** (value true or yes), which result would be **true**
- **1.0** (value 1 with 0 decimals) multiply (times, multiplication) **2.0** (value 2 with 0 decimals), which result would be **3.0**

Notice how similar are the notations in the 4 chosen languages. This is mostly because all four languages belong to the same family of imperative languages, where is most usual to find the infix notation.

Each one of the 4 operations is what we will call an expression. Expressions are the next level of programming building blocks, and represents the smallest unit we can write of something that can be executed: a mathematical operator describes what to do, but without operands there is nothing to do so far. All the 4 examples present one operator and two operands.

### Where can I find my results? Variables.
I know that 1 plus 2 is 3, I do not really need a computer program to calculate that, so what is the point?

The result of an operation can be stored, so we can use it later on. From the cooking point of view this means that will get two ingredients and combine into something: I mix coffee with milk and from now on I will call it cafe late, then I pour the beverage into a cup. The cup becomes the vessel of the result of my operation (the mix) and from this point on, if I need to do anything else with the beverage I will just use the cup: instead of delivering the cafe late to the client, I will just hand over the cup.


| no cup        | Python (no variables):  | 
| ------------- |:-------------:| 
| mix coffee and milk       | ```1 + 2```    | 
| serve coffee to client    | ``` 80 * 1 + 2 ``` |   

| with cup:	 | Python (with variables): |
| ------------- |:-------------:| 
| mix coffee and milk, pour it in a cupi | ```	x = 1 + 2 ``` |
| serve cup to client | ```80 * x ```|

Notice that by using a cup, we are able to serve any kind of brewage to our customers. In the same manner, if we do not use variables in a program (although we can write a pretty big program), we would never be able to compute a different values; since we will write every operand as an specific value.

Variables are the way we have to store the result of computations (during program live time) and have many interesting properties (most of them common to many computer languages), although exact details on how variables work and what can you do with them are specific to the language you are learning, please check your documentation before doing assumptions.

And.. How would this look like in any of the other languages:

#### C
```C
int x = 1 + 2;
80 * x;
Notice the int word? This introduces us to the typing of expressions.
```
### First headache, Types.
No matter what you hear, every programming language is typed. The type concept is common to every language and it is there to help you out (although you might sometimes thing the opposite).

The kitchen can be sorted out as well along categories of tools, foods and crew members. For example: we have fruts (oranges, apples, bananas...) and we have meat (veal, pork, lamb...). When cooking a given main dish recipe, we are meant to use some kind of meat. But if instead of meat we use some fruit, then the results will be un-orthodox, leading us to a new horizon of gastronomic success or a weekend of stomachache.

The problem is that we did not mean the recipe to be used with fruits, and therefore results would be unexpected. In order to guarantee success with the recipe we will annotate the kind of food we want to use. Whenever to apply the restrictions or be more relaxed, depends on the cook.

In the same manner the cook decides whenever being more or less strict about restrictions, programming languages are more or less strict about adaptations taken to make the current values fit in place.

#### Python
``` Python
a = 10 # a is now an Integer number container
b = 10 + a # b is an Integer number container
c = 1.0 + a # c is a Real number container
```

#### C
``` c
int a = 10; // a is an Integer number container
float b = 10 + a // b is a Real number container
                 // 10 + a is an Integer value
int c = 1.0 + a  // c is an Integer container
                 // 1.0 + a is a Real number value
```
The main difference between the last two snippets is that Python does not require to declare the variable type while C does. This does not mean that Python lacks of types, it means that the type of the variable will be adapted to whatever we store in it. On the other hand, in C the variable knows the type it can hold, and it will mold the value we try to fit whenever it is possible.

Every expression in any language has a type. Just like cooking: some broth and toppings of any kind makes a soup while some sweet dough with some icing makes a cake. Whenever you serve the cake in a pan, dish or chopping board depends on how picky the cook is.

Languages can be more or less type sensitive: the big picture here is that some languages like JavaScript or Python are able to infer the type of a given variable from the expression we use to initialize it, and other languages force us to write up front what kind of content this container is going to hold.

A word of warning: serving soup on a flat dish may turn in disaster, having appointed in the recipe to use a bowl may make life easier on the long cooks. I have experienced that strongly typed languages are more robust as the project grows, while dynamic typing is much faster (to develop and test) in the early prototyping phases. You may choose your weapon depending on the scope and resources available.

### I do what I want. Control flow.
So far we have learned how to execute arithmetic operations and somehow tailor them into an arbitrary complex equation. This could be pretty useful but so far we are very little flexible regarding options, repetitions and unexpected scenarios.

Let's draft a new recipe:

#### How to cook potatoes:

- Wash potatoes
- Cut potatoes in half
- Salt half potatoes
- Heat up oven 180ºC
- Cook for 25-30 mins. Depending on size. Check till skin becomes wrinkled.
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
Every expression is an statement on its own, no matter how complex turns to be. The end is marked by an end of statement token, which in case of C, C++, Java, JavaScript, Rust and others is a semi-colon ( ; ) character, while other languages like Python use the end of line. The end of line is an invisible character that text software use to mark where a line ends and a new one begins. In other words, In Python we write one statement per line while in the _C, C++, Java, Javascript and Rust _we are allowed to write more than one (still though I may have something to say about this in the style section).

## Control Flow

Now that we are able to describe steps, is time to address the second and main new issue in the current recipe:

_"Cook for 25-30 mins. Depending on size. Check till skin becomes wrinkled"_

How can we do this? so far we are only able to execute one operation after another. To be able to break a series of statements and switch to other series of statements we need a common feature of imperative languages: control flow.

Our cook is cooking following the instructions and begins to cook the the potatoes in the oven.

1. He opens the oven and lays the potatoes inside.
2. He closes the oven.
3. He waits some time.
4. He opens the oven.
5. He checks if the skin looks wrinkled: If it does not, he goes back to point 2 Otherwise continues in 6
6. Takes the potatoes out of the oven.
Step 5 is slightly more complicated than other steps we have seen before. This is because it is a conditional statement.

There are many flavors in conditional statements and some languages may provide even more, nevertheless there are only 2 significant groups:

Forking conditions.
Loop conditions.
A forking condition enables one path of steps or another depending on a given decision:

_"If the potatoes big, cut them in 4 pieces, otherwise, cut them in half."_

This condition will prepare the cook to handle two possible scenarios. Although we do not know what kind of potatoes he may find in the kitchen, our recipe is ready.

The first and only tool to write less: Functions.
Enough! Ready to write the first program.

