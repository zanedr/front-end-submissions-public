### Question 1

Write a function that will take this array of objects and return an object that counts up all the `groceryList` items

var array = [
  {name: 'yung-jhun',
  groceryList: ['grapes', 'avocados', 'chicken', 'tortillas', 'rice']},

  {name: 'alter-nate',
  groceryList: ['chips', 'kale', 'cheese', 'tortillas', 'rice']},

  {name: 'taylor',
  groceryList: ['chips', 'eggs', 'tomatoes', 'tortillas', 'rice']}
]

=> { grapes: 1, avocados: 1, chicken: 1, tortillas: 3, rice: 3, chips: 2, kale: 1, cheese:1, eggs:1, tomatoes, 1}

### Question 2

Write a function that takes this large object and returns a new object with two keys `yongerThan15` && `olderThan15`. The interaction should look like this:

```
var objects = {
  person1: {name: 'taylor', age: 11},
  person2: {name: 'jhun', age: 12},
  person3: {name: 'alter-nate', age: 16},
  person4: {name: 'meeka', age: 16}
}

// return an object that looks like this

{
  yongerThan15: [{name: 'taylor', age: 11}, {name: 'jhun', age: 12}]
  olderThan15: [{name: 'alter-nate', age: 16}, {name: 'meeka', age: 16}]
}

```

### Question 3

Explain the differences between bracket notation, and dot nation. In what situations would brackets be better to use than dot?

### Question 4

 * Explain what is being logged
 * Explain why it's being logged
 * Explain the difference between block and global scope.

```
let array = [];

for (var i = 0; i < 10; i++) {
  array[i] = function () {
    console.log('You clicked: ' + i);
  };
}

array[5]() // what will log here?

```

```
let array = [];

for (let i = 0; i < 10; i++) {
  array[i] = function () {
    console.log('You clicked: ' + i);
  };
}

array[5]() // what will log here?

```

### Question 5

Consider the following code.

```
function Hoodlum1 (name, alterEgo) {
  this.name = name;
  this.secret = {
    name: alterEgo,
    getName: function () {
      return this.name;
    }
  }
}

```
```
function Hoodlum2 (name, alterEgo) {
  this.name = name;
  this.secret = {
    name: alterEgo,
    getName: () => {
      return this.name;
    }
  }
}

```

Answer the following questions:

  * In Hoodlum1 when you call `getName` function what is being logged and why?
  * In Hoodlum2 when you call `getName` function what is being logged and why?
  * In Hoodlum1 how can I get the `getName` function to log the `alterEgo` value?
