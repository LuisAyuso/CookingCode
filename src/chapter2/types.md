## First headache, Types.
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

