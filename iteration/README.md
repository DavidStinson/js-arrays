# Intro to JS Arrays - Iteration

![Hero image](./assets/hero.png)


## Iterating Over All of the Elements in an Array

### Using the `forEach` Iterator Method

Although a `for` loop can be used to iterate over an array, if we want to iterate over **all** of the elements in an array, the [forEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) iterator method is a better approach because it more clearly communicates the developer's intention:

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

As you can see, the `forEach` method calls the function provided as an argument **once for each element** in the array.
	
If you need to know the index of the current iteration, the `forEach` method also happens to pass in the index as a second argument, for example:

```js
movies.forEach(function(movie, idx) {
  console.log(idx + ' - ' + movie);
});
```

...will result in the following output:

```
0 - Best In Show
1 - Alien
2 - The Matrix
3 - Gladiator
```

It's a **best practice** to name the first parameter that accepts each element as the singular version of the name of the array, or simply the first letter of the array variable (`movie` or `m` for the example above).

### Using a `for...of` Loop

ES2015 provides the `for...of` loop for iterating over the elements of arrays and other iterables such as strings:

```js
for (let movie of movies) {
  if (movie === 'The Matrix') break;
  console.log(movie);
}
```

...will result in the following output because once `movie` is assigned 'The Matrix', the `if` statement will result in exiting the `for` loop thanks to the `break` statement:

```
Best In Show
Alien
```

Whereas the `forEach` method always iterates over every element, the `for...of` loop can be exited using the [break](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/break) statement.

Note that there is also a `for...in` loop with similar syntax.  We will learn more about this type of loop later, but for now be careful not to accidentally use `for...in` when you intend to use `for...of`.
