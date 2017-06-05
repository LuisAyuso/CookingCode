## Where can I find my results? Variables.
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

And... How would this look like in any of the other languages?

#### C
```C
int x = 1 + 2;
80 * x;
```
Notice the int word? This introduces us to the typing of expressions.


