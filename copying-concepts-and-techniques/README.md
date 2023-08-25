![Hero image](./assets/hero.png)

# Intro to JS Arrays - Copying Concepts and Techniques

When working with arrays in JavaScript, there are scenarios where you might want to create a copy of an array rather than modifying the original one. This can prevent unintended side effects in your code, or you might want to derive a new list from the original without affecting it.

## Making Copies of an Array

There are multiple methods to copy an array. The method you choose largely depends on whether you wish to copy a segment of the array or the entire array itself.

Let's take a look...


### Copy All of an Array

ES2015 introduced the [Spread syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax).  `...` , a concise way to duplicate an entire array:

Example:

```js
let movies = ['Best In Show', 'Alien', 'The Matrix', 'Gladiator'];
const moviesCopy = [...movies];
console.log(moviesCopy); //-> ['Best In Show', 'Alien', 'The Matrix', 'Gladiator']
```
All elements from the `movies` array have been "spread" into the new array.


### Some of an Array

If you want to copy just a portion of an array, the [slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) method comes in handy. This method always returns a new array and, more importantly, doesn't modify or *mutate* the source array.

> :books: In coding, when we say *mutate*, we mean changing a piece of data directly without making a separate copy of it. So, if you change it in one place, it changes everywhere else you're using it too.

The syntax for `slice` is as follows:

`array.slice(startIndex, [endIndex])`

Here, the second argument is the ending index but does not include the value at that index in the result.

Example:

```js
let movies = ['Best In Show', 'Alien', 'The Matrix', 'Gladiator'];
const twoMovies = movies.slice(1, 3);
console.log(twoMovies); //-> ['Alien', 'The Matrix']
```


### Copy an Array and Insert Additional Elements

Here's how you can copy an array and insert additional elements simultaneously using the spread syntax:

```js
const twoMovies = ['Alien', 'The Matrix'];
const fourMovies = ['Amadeus', ...twoMovies, 'The Sting'];
console.log(fourMovies); //-> ['Amadeus', 'Alien', 'The Matrix', 'The Sting'];
```

### Shallow vs. Deep Copies in Arrays

- **Shallow vs. Deep Copy**: Important to note the techniques we've discussed here perform a **shallow copy** of the array. This implies that if your array has objects, the copy will reference the same objects, not create fresh ones. Therefore, any modifications to the objects in the original array will be reflected in the copied array.

 - A **deep copy** creates a new array (or object) and also creates copies of every element or property, even if they are objects or arrays themselves. This ensures that the new copy is entirely independent of the original.

- **Performance Implications**: When you're dealing with extensive arrays, some methods might use more memory than others. Depending on your specific needs, choose a method that offers optimal performance. 
