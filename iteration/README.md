# Intro to JS Arrays - Iteration

![Hero image](./assets/hero.png)


Arrays are fundamental in JavaScript, and often, we need to process each item in an array. This action is known as *iteration*. 

> :books: *Iteration* is the process of repeatedly executing a set of instructions or looping through a collection of items (like an array or string) one by one until a certain condition is met or until there are no more items left to process.

## Using the `forEach` Iterator Method

While the traditional `for` loop can be used to iterate over an array, the [`forEach`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) method is a more expressive and readable way to iterate over **all** array elements. This method clearly showcases a developer's intention to process each item.

Let's try it out:

```js
movies.forEach(function(movie) {
  console.log(movie);
});
```

...will result in the following output:

```
Best In Show
Alien
The Matrix
Gladiator
```


The `forEach` method invokes the provided function once **for each item** in the array.

To access the current item's index, `forEach` provides it as a second argument:


```js
movies.forEach(function(movie, index) {
  console.log(index + ' - ' + movie);
});
```

This will result in the following output:

```
0 - Best In Show
1 - Alien
2 - The Matrix
3 - Gladiator
```

**Best Practice**: It's recommended to name the first parameter (representing each item) as a singular form of the array's name. So, if your array is named `movies`, name the parameter `movie`.


## Using a `for...of` Loop


Introduced in ES2015, the `for...of` loop offers a concise way to iterate over arrays (and other iterable structures like strings):

```js
for (let movie of movies) {
  if (movie === 'The Matrix') break;
  console.log(movie);
}
```
This results in the following output: 

```
Best In Show
Alien
```

The loop breaks, or exits early, when it encounters 'The Matrix' thanks to the [break](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/break) statement. This highlights that, unlike `forEach`, the `for...of` loop provides more control, such as the ability to exit early.


:warning: **Caution**: JavaScript also provides a `for...in` loop. It's designed mainly for iterating over an object's properties rather than array items. Be sure you're using the correct loop for your needs.
