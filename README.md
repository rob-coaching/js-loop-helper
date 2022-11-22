# Helper for Coding Challenges

Each coding challenge has an INPUT, usually an ARRAY.

And we should write a function which produces some OUTPUT from the given INPUT.

So how do we get from INPUT to the desired OUTPUT? 

Can we use some strategy to make it easy for us to start?

## The INPUT to OUTPUT table

By analyzing the demanded OUTPUT, we usually can decide which JS methods to use quite easily!

### Scenario 1 - Input = ARRAY. Output = ARRAY

Now it is time to analyze WHAT operation should be applied to get to the OUTPUT array.

#### Case I: Querying / Filtering

If after our function the amount of items in the OUTPUT Array should be LESS than the amount of INPUT items, that typically means we should FILTER some items out!  

Loop candidates: `filter or forEach`

Example: 

```
INPUT Fruit array : ['apple', 'banana', 'banana', 'apple', 'apple']
OUTPUT: New array with all apple items: ['apple','apple','apple']
```

#### Case II: Change / Update / Format

If after our function the AMOUNT of items in the OUTPUT array should stay THE SAME than in the input array, typically we don't need to filter anything.

Instead we must loop through ALL items and CHANGE either one or several elements.

Loop candidates: `map, forEach`

Example:

```
INPUT: ['apple', 'banana', 'cherry']
OUTPUT: ['APPLE', 'BANANA', 'CHERRY'] (uppercase all items!)
```

Now we have to decide two sub cases:
1) Shall we update the ORIGINAL array? (=mutation)
2) Shall we create a NEW array, keeping the original untouched? (= create copy)

Mutating original: use `forEach` loop (go to each item and update):

`fruits.forEach((fruit, index) => fruits[index] = fruit.toUpperCase()) // changes original`

Creating new array / copy: use `map` loop:

`const fruitsCopy = fruits.map(fruit => fruit.toUpperCase()) // creates copy`

### Scenario 2 - Input = ARRAY. Output = OBJECT

#### Case 1: Find a certain item by criteria

This is the easiest case. We look for a certain item, so just ONE item, in the array.

Loop candidates: `find // (forEach or reduce are not really helpful here...)`


#### Case 2: Create Statistics

In case we want to BUILD UP an object with NEW info, we typically wanna build some statistics (e.g. counting items or calculating sums)

Example: 

```
INPUT: ['apple', 'apple', 'banana', 'apple']
OUTPUT: { apple: 3, banana: 1 } // count up all items found 
```

Loop candidates: `reduce or forEach // (as default we use an empty object in both cases)`

### Scenario 3 - Input: ARRAY, Output: Number oder String 

In this case we want to loop over all items and usually want to count something up, build a sum or concatenate certain .items

Example I: 
```
INPUT: [1,2,3,4]
OUTPUT: SUM // 10
```

Example II:
```
INPUT: ["apple", "apple", "banana", "apple"]
OUTPUT: COUNT of apples // 3
```

Example III:
```
INPUT: ["G", "a", "e", "l]
OUTPUT: "Gael"
```

Loop candidates: `reduce, forEach`

In case we want to build up a NUMBER we start with 0 as default.

In case we want to build up a STRING we start with "" as default.

### Scenario 4 - Input: Number, Output: Array 

Loop candidates: WHILE Loop or FOR Count Loop (using i)

Example: 

You have a number, e.g. 2 (EUR)
We want to exchange this into an array of quarters (25 Cent)

```
INPUT: 2
OUTPUT: [25,25,25,25,25,25,25,25]
```

We will likely produce MORE output items than we have input items. Then we typically use the WHILE loop.

But we usually can also ALWAYS use a for i loop (for counting loop) to do the same.

Other case: We get some input and don't know in advance how many items we have to loop over.

Example: 
We get a file and need to process all files in there. But we don't know how many lines the file has. In this case often the WHILE loop is used until we reached the END of the file (=no more lines available => stop)

### Summary 

And there we have it!

These are the common scenarios to get started with probably more than 90% of all code challenges!

Once you have a good understanding on determining which OUTPUT is demanded, which INPUT is given and which tool to use to get from INPUT to OUTPUT you are already half way there!

ENJOY the challenge :D
