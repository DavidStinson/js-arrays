![Hero image](./assets/hero.png)

# Intro to JS Arrays - Iteration

**Learning objective:** By the end of this lesson, students will be able to *iterate* through and carry out actions on each element in an array.

___
:books: *Iteration* is the process of repeatedly executing a set of instructions or looping through a collection of items (like an array or string) one by one until a certain condition is met or until no more items are left to process.
___

## Using the `forEach()` iterator method

While the traditional `for` statement can be used to iterate over an array, the [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) method is a more expressive and readable way to iterate over **all** array elements. This method clearly showcases a developer's intention to process each item.

Let's try it out:

```js
// as a reminder, movies is ['Barbie', 'Get Out', 'John Wick']

movies.forEach(function(movie) {
  console.log(movie);
});
```

___
:trophy: It's recommended to name the first parameter (representing each item) as a singular form of the array's name. So, if your array is named `movies`, name the parameter `movie`.
___

This code will result in the following output:

```text
Barbie
Get Out
John Wick
```

The `forEach()` method invokes the provided function once **for each item** in the array.

`forEach()` provides it as a second argument that can be used to access the current item's index:

```js
movies.forEach(function(movie, index) {
  console.log(index + ' - ' + movie);
});
```

Which will result in the following output:

```
0 - Barbie
1 - Get Out
2 - John Wick
```

## Using a `for...of` loop

The `for...of` statement offers a concise way to iterate over arrays (and other iterable structures like strings):

```js
for (let movie of movies) {
  if (movie === 'Get Out') break;
  console.log(movie);
}
```
This results in the following output: 

```text
Barbie
```

The loop exits early when it encounters 'The Matrix' thanks to the [break](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/break) statement. This highlights that, unlike `forEach()`, the `for...of` statement provides more control, such as the ability to exit early.

___
:warning: JavaScript also provides a `for...in` loop. It's designed mainly for iterating over an object's properties rather than array items. Be sure you're using the correct loop for your needs.
___
