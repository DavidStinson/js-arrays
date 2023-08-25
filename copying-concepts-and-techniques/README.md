# Intro to JS Arrays - Copying Concepts and Techniques

![Hero image](./assets/hero.png)

## Making Copies of an Array

There are multiple ways to copy an array.

The approach you use depends upon whether you need to copy just some or the entire array.

Let's take a look...

### Copy All of an Array

ES2015 gave us a cool new way to copy an entire array using `...` ([Spread syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)).

Example:

```js
movies //-> ['Best In Show', 'Alien', 'The Matrix', 'Gladiator']
const moviesCopy = [...movies];
moviesCopy //-> ['Best In Show', 'Alien', 'The Matrix', 'Gladiator']
```
All of the elements in the `movies` arrays have been "spread" within the new array.

### Some of an Array

We can use the [slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) method to create part (or all), of an array.

The `slice` method always returns a new array and does not mutate (change) the source array.

`slice` has a syntax of:<br>`array.slice(startIndex, [endIndex])`

Unlike `splice`, the 2nd argument in `slice` represents the ending index (but does not include that index). 

Example:

```js
movies //-> ['Best In Show', 'Alien', 'The Matrix', 'Gladiator']
const twoMovies = movies.slice(1, 3);
twoMovies //-> ['Alien', 'The Matrix']
```

### Copy All of an Array & Insert Additional Elements

Here's how you can copy and insert additional elements simultaneously using the spread syntax:

```js
twoMovies //-> ['Alien', 'The Matrix']
const fourMovies = [ 'Amadeus', ...twoMovies, 'The Sting' ];
fourMovies //-> ['Amadeus', 'Alien', 'The Matrix', 'The Sting'];
```
