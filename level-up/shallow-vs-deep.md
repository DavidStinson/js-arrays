# Shallow vs. Deep Copies of Arrays

![Hero image](./assets/hero.png)

**Shallow vs. Deep Copy**: It's important to note that the techniques we've discussed in this module perform a **shallow copy** of the array. This implies that if your array has objects, the copy will reference the same objects, not create fresh ones. Therefore, any modifications to the objects in the original array will be reflected in the copied array.

Want to see this in action? Try this out on the `movies` and `twoMovies` arrays from the lecture:

```js
console.log(movies);
console.log(twoMovies);

movies[1] = 'Spider-man';

console.log(movies);
console.log(twoMovies);
```

  This can be a huge pain point in an application, so be careful of this behavior!

A **deep copy** also known as a **deep clone** creates a new array (or object) and also creates copies of every element or property, even if they are objects or arrays themselves. This ensures that the new copy is entirely independent of the original.

With a deep copy, the entire structure is duplicated, making the two arrays completely independent. There are a couple of ways to do this.

- The older technique of using the `JSON.stringify()` method combined with `JSON.parse()`. This is not preferred as it doesn't retain all types of data in its original form.
- The newer [`structuredClone()`](https://developer.mozilla.org/en-US/docs/Web/API/structuredClone) global function, demonstrated below

  ```JS
  let movies = ['Best In Show', ['Alien', 'The Matrix'], 'Gladiator'];
  let deepCopy = structuredClone(movies);

  deepCopy[1][0] = 'Prometheus';

  console.log(movies);      // Outputs: ['Best In Show', ['Alien', 'The Matrix'], 'Gladiator']
  console.log(deepCopy);    // Outputs: ['Best In Show', ['Prometheus', 'The Matrix'], 'Gladiator']
  ```

Keep in mind you don't always need to deeply clone something - you should only do this when you need to make a full independent copy of an array because deeply cloning it effectively doubles the memory consumed by the data.
