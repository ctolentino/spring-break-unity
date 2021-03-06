#C-Sharp For Beginners

An in-depth introduction to some basic programming terms for those who have never coded before.

####Variables

A _variable_ is like a word in the C-Sharp language. It stands for a concept throughout your code. Say you want to represent your age in C-sharp. You could do something like this:

`int age = 14;`

C-Sharp won't know what "age" means until you assign it a meaning. By saying "my age _equals_ 14", your script now knows that any time it sees "age" that it means 14. But why the effort of making a variable? One thing that variables do for us is that we only need to assign them once, even if we reuse them many times. If you come back to your script next year and need to change your age to 15, would you rather go through your program and find every time "14" appears and replace it yourself, or just change "age = 15" and be done with the whole thing?

Think of a variable like a box with a label on it. We want the label to tell us something about what the thing inside. If I named the "age" variable something like "bananas", anybody else reading my code wouldn't be able to tell what it meant. Or worse, if I left this code alone for a long time and came back to it, even though I wrote it I wouldn't remember what it was supposed to be doing. Making a full game takes a long time, especially if you want to do it by yourself, and using good variable names really helps you and anyone else you might be working with understand your code.

Variables have to be all one word, and can't have spaces in them. It's best to just use a word or phrase that describes it, but if you use multiple words, capitalize anything after the first word so it's easier to read. For example: `bool isActiveAndEnabled = true;`

You can change the contents of a variable whenever you like, even if it's already been assigned to. If the box is in a spot on the top shelf of a refrigerator, it doesn't matter whether you put cheese, eggs or ham in it, but there can only be one thing in that position at a time, so the previous value gets taken out before the new one is put in. But, just like this example, there are some rules with variables in C-Sharp. You wouldn't put your phone or your cat in the refrigerator, because it doesn't belong there!

####Data types
This is because, in C-Sharp, all variables have a _data type_. This means that this specific box can only hold one kind of item. C-Sharp is very strict about the right data type going into a variable. Remember when we made the "age" variable above?

`int age = 14;`

We put the word "int" in front of the variable name to tell C-Sharp that this variable will hold an integer. (If you remember integers from algebra, it's the same kind of number--as a refresher, an integer is any whole number and can be positive or negative.) If we try to say our age is "banana", which isn't an integer, C-Sharp will refuse to play along and stop the program right there.

Here are some common data types in C#:

- Integer: This is a whole number. It can be positive or negative. There is a maximum and minimum size for integers in C-Sharp: 2,147,483,647. Integers are exact and are good for things like hit points, attack power, number of coins, games with strict grid-based movement, and other things.
- Float: A float is short for a floating-point number. Floats can handle decimal points, and also scientific notation, so they can handle very small numbers close to zero and also very large numbers much bigger than integers. However, the way they're stored by the computer means that they're not 100% precise at the very smallest and very largest ranges. Floats are used for most number calculations in Unity, since they can handle division and multiplication better than integers. One important thing to know about floats is that they can also hold whole numbers, but C-Sharp will think you mean the whole number is an integer unless you add "f" to the end of the number. So you might see: `float speed = 1f;`
- Boolean: A boolean (bool for short) is just a true-false question for the computer. Booleans can only hold "true" or "false". They are the simplest data type to store. These work well with bits of code that need to check if a condition is true before doing something. For example: `bool isPlayerOne = true;` would let us use the isPlayerOne variable to do some actions differently for Player One.
- Char: A _character_ or "char" for short is a single letter, symbol, or emoji. A char can store standard English letters and keyboard symbols natively, by using: `char spaceBar = ' ';` Notice that char uses single-quotes. Letters or characters from other languages, or symbols and emoji, can be added using their Unicode representation, with '\u' in front. For example, if I look up the infinity symbol ∞, I can find its Unicode value is 221E, so I can use it in a script with this line: `char infinitySymbol = '\u221e';`
- String: A _string_ is just a bunch of characters strung together into a word, phrase, or sentence. You can make a string by combining a bunch of characters, or write it out the easy way by putting the text you want the string to contain in double quotes. A string declaration looks like this: `string playerName = "Super Mario";`

Unity also has its own data types, which we can access through the `using UnityEngine;` line that Unity puts in the script for us. Here are some common ones:

- GameObject: This is Unity's data type for any object that's in your game. If you want a variable to hold an entire GameObject and anything attached to it, you would use something like: `GameObject player = GameObject.Find("Player");`
- Transform: Every GameObject has a Transform, which holds information about an object's position, rotation and scale. In turn, the position, rotation and scale are stored as...
- Vector3: A Vector3 is a data type that holds three floats named x, y and z. It's commonly used to store an object's position in the world. So we could do something like this: `Vector3 playerPosition = player.transform.position;` Vector3 is also used to store things like the direction an object is moving, and how fast it is moving in all three directions at once. We will be using Vector3 a lot in making a game.

####Operators

C-Sharp understands all standard math operators. These will work on any int or float variable. The + operator can also work on strings and chars to combine them, but none of the others will work on data types that aren't meant to hold numbers.

- Add: use `+`.
- Subtract: use `-`.
- Multiply: use `*`.
- Divide: use `/`.
- Get the remainder of a division ("modulo"): use `%`. (So, 17 % 5 = 2, because 5 goes into 17 3 times but has a remainder of 2.)

There are also some operators for comparison, which work like standard math comparisons. These will give us a "true" or "false" value that we can store in a boolean variable.

- Greater than: `>`. So, 5 > 3 will give us "true".
- Greater than or equal to: `>=`.
- Less than: `<`. So, 5 < 3 will give us "false".
- Less than or equal to: `<=`.
- Equal to: `==`. *Since we use a single equal sign to assign to variables, we have to use a double equals sign to ask if two values are equal without assigning the second value to the first.*
- Not equal to: `!=`.

####Conditionals

Conditionals are a way to tell the script, "if this condition is true, do this thing; if it's not, do this other thing." Conditionals use boolean values to check if they should do any code within the if-block. An example:

```
if(playerHealth > 0) {
  Attack();
} else {
  Die();
}
```
This will only do Attack() if the player has more than zero health. Once it does the 'if' part, it ignores the 'else' part. Otherwise, if the player's health is NOT greater than zero, it will ignore the Attack() command and jump straight to Die().

There are some additional operators that work on boolean values.
- AND: `&&`. The whole statement will be true only if all statements joined by an `&&` are true. `if(playerHealth > 0 && playerMP > 0) { ... }`
- OR: `||` The whole statement will be true if at least one of the statements is true. `if(health <= 0 || timer <= 0) { ... }`
- NOT: `!` will use the opposite value of the statement. For example, if you wanted to attack only if the player is NOT dead, you might use: `if(!playerDead) { Attack(); }`

####Loops

A loop is a set of actions that will run while a condition is true. We use loops to do actions multiple times, expecially if we have a collection of objects and we need to do something to each of them. We'll mostly be using a _for loop_, like this one:

```
int count = 5;
for (int i = 0; i < count; i++) {
  score++;
}
```

A for loop has three parts: starting the counter, the condition that must be true for the loop to run, and what happens to the counter at the end of each item in the loop. This loop will start a counter variable `i` at zero, and, while `i` is less than the number `count`, it will do the action inside the braces and then do the last action in the for loop. The `++` after an integer variable is a short way of telling it to do `i = i + 1;`.

This is part of a bit of code that will make the player's score slowly count up when they win points, instead of it happening all at once.

####Functions

If variables are the nouns, functions are the verbs. Functions tell C-Sharp what to do with our variables. Let's look at an example.

`void Start() {
}`

This is an empty function like the one Unity generated for us when we created this script. The first word, "void" tells us that this function gives us nothing back when we call it. Then we have the function name, and some parentheses with nothing in them. The parentheses are where any data that the function needs to take in will go. This one doesn't need any outside data to do its job, so that part is blank. Finally, the curly braces surround the actions that this function is taking. Let's look at a function which will actually do something.

`string WelcomeMessage(string name) {
  return "Hello, " + name;
}`

We see that `void` has changed to `string`, because this function _returns_ a string when it is run. It also takes in data, which is a string variable called `name`. Data that a function takes in is called a parameter.

When a function has a return type, we can store the data it returns in a variable of the same type. So, we could do this:
`string message = WelcomeMessage("NyanCat");`
and then `message` will contain: `"Hello, NyanCat"`

We _call_ a function by writing its name with parentheses after it. The parentheses must contain any data that the function needs to run. If it does not take any parameters, it will simply look like: `int number = GenerateRandomNumber();`

C-Sharp will raise an error if a function is called with the wrong type or number of arguments. One thing C-Sharp does to make things easier with this problem is called _function overloading_. We can make different versions of the same function that take diferent parameters, and C-Sharp will know which one to run based on the parameters given when it is called. So, we could write another function:
`string WelcomeMessage() {
  return "Hello, person"
}`
and if we call WelcomeMessage() without passing it a name, C-Sharp will run the version of the function that doesn't need any parameters.
