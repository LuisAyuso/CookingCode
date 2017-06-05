## The first and only tool to write less: Functions.

When cooking, there are some steps which can be described once and then used more than one time. For example: _cutting vegetables_.

#### How to cut vegetables:

1. Get a knife.
2. Get a Copping board.
3. Choose an end of the vegetable and put the sharp side of the knife in contact with it.
4. Move the knife edge 1/4 of an inch closer to the remaining vegetable. 
5. Apply pressure in the knife until a slice is created.
6. If the remaining vegetable is larger than 1/4 of an inch repeat from 4. Otherwise continue.
7. Clean the knife and the chopping board.

I guess no one will ever describe this process like I just did; probably using knifes in an inherent skill of the human kind. Nevertheless, this example serves us to illustrate the idea: 

Whenever I would like to cut a carrot, pepper, or any other vegetable, I will just follow the steps described before.It does not matter what actual veggie do I need for my current recipe, and following the steps will most probably work out. 

In a more orthodox way of phrasing it: Cutting a veggie is a function which accepts a veggie as parameter and the result is a group of slices. In a recipe you may find one instruction which states: _cut the carrots_. In our programming  languages world, this means to apply the function _cut_ to the value _carrot_ of type _veggie_.

When describing a function, there are 3 steps to keep in mind. 
- The call: When we use the function, we execute the steps it describes with an input.  
- The prototype: This "thing" describes how your function is named, what do we need to execute it and what will be the result.
- The definition: The list of steps which tells us what to do. 

#### The call

To use the code packed in a function, we just need to apply it to a given input.

| In the Kitchen  | Python | C |
|:---------------:|:------:|:-:|
| cut a carrot    | ```abs(1) ``` | ```abs(1)``` |
| cut a pepper    | ```abs(2)``` |``` abs(2)``` |
| mix coffee and milk | ```sum(1, 2)``` | ```sum(1, 2)``` |
| mix soup and cream  | ```sum(1.0, -1)``` | ```sum(1.0, -1)``` |
 
Although using the function seems pretty similar in every language, the differences come when we want to describe their behavior.

#### Prototype

A very important part of a function is to give it a name, so people know what you mean by using it. When cooking, there are many _functions_ available to you. You can _boil_, _fry_, _bake_, or _grill_; each of them manage to cook your food by applying heat, some other side effects may appear though.

A cook knows a _repertoire_ of functions: like how to _boil_ meat, or _fry_ fish; in this way, when he writes a recipe he my skip the tedious task of explaining truisms. At the same time, the cook may want to separate the description of how to prepare the sauce from the main dish list of steps. This side story will be acknowledged in the recipe with one steps stating: _now you can cook the sauce_. By doing so we can reduce the level of detail needed, and make our recipe easier to read.

After the name, a list of requirements is always needed. This list will describe what needs to be provided to get the job done. In the case of _pealing a vegetable_ it will be a veggie, which later on can be any kind of actual veggie: like a carrot or a potatoe. In the case of _mixing two liquids_: we will need two liquids, which can be coffee and milk, gin and tonic, or even beer and Cocacola (barbaric).

To finalize the prototype, we will note what is it that our operation will create: we put together some ingredients t  make a cake, or a sauce, or a soup...

Puting together the three parts: We have the title of our little recipe:

_To boil veggies_
- We will need some vegetable.
- We will get a boiled vegetable.

The following examples show the prototypes for the absolute value funcion:

| C++ | Rust | Python |
|:------:|:-:|:------:|
| ```int abs(inti value)``` | ```fn abs(value: i32) -> i32``` | ```def abs(value):``` |

Notice that python does not state what kind of value the function returns. Dynamic typing languages do not need this as they constattly addapt to the current context, as work like some kind of teenager kid who addresses everything by _stuff_. This does not mean that functions do not have a return type, it means that functions allways return some stuff, and then you can put it on a stuff container and make some other thing with this stuff.

### Tweak a function

#### Parameters:

In case I move to live to the other side of the world 
