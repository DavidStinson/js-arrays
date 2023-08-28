# Intro to JS Arrays - Level Up

![Hero image](./assets/hero.png)

Here's some level up work related to JavaScript arrays!

## Shallow vs. deep copies of arrays

- **Shallow vs. Deep Copy**: It's important to note that the techniques we've discussed in this module perform a **shallow copy** of the array. This implies that if your array has objects, the copy will reference the same objects, not create fresh ones. Therefore, any modifications to the objects in the original array will be reflected in the copied array.

  Want to see this in action? Try this out on the `movies` and `twoMovies` arrays from the lecture:

  ```js
  console.log(movies);
  console.log(twoMovies);

  movies[1] = 'Spider-man';

  console.log(movies);
  console.log(twoMovies);
  ```

  This can be a huge pain point in an application, so be careful of this behavior!

- A **deep copy** also known as a **deep clone** creates a new array (or object) and also creates copies of every element or property, even if they are objects or arrays themselves. This ensures that the new copy is entirely independent of the original.




- With a deep copy, the entire structure is duplicated, making the two arrays completely independent.

- Using the JSON methods (with its known limitations):

  ```JS
  let movies = ['Best In Show', ['Alien', 'The Matrix'], 'Gladiator'];
  let deepCopy = JSON.parse(JSON.stringify(movies));

  deepCopy[1][0] = 'Prometheus';

  console.log(movies);      // Outputs: ['Best In Show', ['Alien', 'The Matrix'], 'Gladiator']
  console.log(deepCopy);    // Outputs: ['Best In Show', ['Prometheus', 'The Matrix'], 'Gladiator']
  ```

When you're dealing with extensive arrays, some methods might use more memory than others. Depending on your specific needs, choose a method that offers optimal performance. 