# Intro to JS Arrays - Level Up - `at()`

![Hero image](./assets/hero.png)

## The `at()` method

Unlike other programming languages, JavaScript does not support negative indexing using square bracket. Attempting to access an array element with a negative index will result in a value of `undefined`.

```js
movies[-1];  // undefined
```

In ES2022, the [`at()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/at) method was added to the JavaScript spec. The `at()` method can directly access elements by their index. It's not that different from square bracket notation at first glance, except it does accept negative indexes! This can be used to access the last item in an array easily:

```js
const lastMovieAt = movies.at(-1);  
// lastMovieAt is 'Get Out'
```

The `at()` method improves code readability, especially when executing complex array manipulations.
