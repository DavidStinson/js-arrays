![Hero image](./assets/hero.png)

# JS Arrays - Wrap up

## `join()` and other array methods 

The array `join()` method combines all of the string elements in an array and returns a single string:

```js
// as a reminder, movies is ['Barbie', 'Get Out', 'John Wick']
let movieString = movies.join();
// movieString is 'Barbie,Get Out,John Wick'
```
	
As you can see, by default, the movie strings were separated by a comma. However, we can pass `join()` whatever string we want to use as the separator:

```js
movieString = movies.join(' -- ');
// movieString is 'Barbie -- Get Out -- John Wick'
```

There are many other useful array methods like `join()` above that we haven't covered here. Be sure to reference documentation such as that provided by MDN or do a Google search when you encounter road blocks - often you don't need to reinvent the wheel since many array methods will help complete common tasks.

## :question: Review Questions

<details>
  <summary>(1) In your own words, what's an array?</summary>
  
  An array is a data structure used store an ordered list of data.
</details>

<details>
  <summary>(2) What's the best approach for iterating through an entire array?</summary>
  
  Use the array's <code>forEach()</code> iterator method.
</details>

<details>
  <summary>(3) What array method can remove, insert, and replace any number of elements?</summary>
  
  The <code>splice()</code> method.
</details>

<details>
  <summary>(4) What method might you use to remove a single element from the end of an array?</summary>
  
  The <code>pop()</code> method.
</details>

<details>
  <summary>(5) Assuming the below code, what will the value of the variable <code>color</code> be?</summary>

  <code>'green'</code>
</details>

```js
const colors = ['red', 'green', 'blue'];
let color = colors[1];
```

## Wrapping up

As you saw in this lesson, arrays are incredibly convenient ways to store data. Check out the level up content for more!
