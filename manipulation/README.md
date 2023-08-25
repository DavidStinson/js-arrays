# JS Arrays - Manipulation

![JS arrays manipulation hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to manipulate arrays by modifying their contents and by adding or removing elements anywhere in an array.

## Updating existing elements in an array

Just like we access elements in an array using square bracket notation, we can also use this same syntax to update an element in a specific position:

```js
// recall that movies is ['Barbie', 'Interstellar', 'Get Out']

// Let's update the 2nd movie (index of 1)
movies[1] = 'Arrival';
// movies is now ['Barbie', 'Arrival', 'Get Out']
```

Wait though, isn't `movies` a constant? How are we able to modify its contents? 

When we made `movies` a constant, what we're really telling JavaScript is to not let us change what `movies` is pointing at (a specific array). It is not, however, saying that the contents of that array cannot be *mutated* or altered. In short if we try doing something like the examples below, we'll get an error:

```js
// attempting to change the movies constant to string
movies = 'Barbie and Arrival'
// attemping to change the movies constant to a different array
movies = ['Barbie', 'Arrival']
```

But when we change the contents of the existing array, everything checks out fine!

___
:books: *Mutation* is the modification of the content of a data structure or variable. This contrasts with *immutability*, where data cannot be changed once created.
___

## Adding or removing elements at the start or end of an array

Don't worry, we'll eventually get to adding (and removing) elements anywhere in an array!

### `push()`

We can add one or more elements to the **end** of an array using the [`push()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push) method:

```js
movies.push('Parasite');
// movies is ['Barbie', 'Arrival', 'Get Out', 'Parasite']
```

To add multiple items, pass more than one argument to the method, as demonstrated below with the `unshift()` method.

### `unshift()`

Just like `push()`, [`unshift()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift) allows us to add one or multiple items to an array, this time at the start of the array.

```js
movies.unshift('Dune', 'Coco');
// movies is ['Dune', 'Coco', 'Barbie', 'Arrival', 'Get Out', 'Parasite']
```

Here, you can see we've added two items to the array by passing multiple arguments to the method.

### `pop()`

We can remove a single element from the **end** of an array using the `pop` method:

```js
movies.pop();
// movies is ['Dune', 'Coco', 'Barbie', 'Arrival', 'Get Out']
```

### `shift()`

We can also remove from the **front** of an array with `shift`:

```js
movies.shift();
// movies is ['Coco', 'Barbie', 'Arrival', 'Get Out']
```

`pop()` and `shift()` both only remove one element at a time and don’t take any arguments. These methods both return the element that was removed from the array:

```js
const removedMovie = movies.shift();
// movies is ['Barbie', 'Arrival', 'Get Out']
// removedMovie is 'Coco'
```

### Remembering the `push()`, `pop()`, `unshift()`, and `shift()` methods.

Here's a device you can use to potentially help you remember the functions of all of these methods:

```text
The methods with longer names **add** to an array
unshift -> [...] <- push

The methods with shorter names **remove** elements from an array
shift <- [...] -> pop
```

Don't get too caught up in trying to remembering things like this though, MDN, Google, and AI assistants are there to help you remember the things you might get turned around on.

## Adding and removing elements anywhere in an array

The [**Array.prototype.splice**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) method can add or remove any number of elements to/from an array with a single line of code!

[Array.prototype.splice() - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

`splice()` has a syntax of: `array.splice(start, deleteCount, newItem1, newItem2...)`.

Examples of adding/removing elements with `splice()`:

```jsx
let movies = [ 'Caddyshack', 'Interstellar', 'Scarface', 'Trading Places', 'Iron Man' ]
//							    0              1             2              3              4
let removedMovies = movies.splice(3, 2, 'Spaceballs', 'Alien')
// removedMovies is ['Trading Places', 'Iron Man']
// movies is ['Caddyshack', 'Interstellar', 'Scarface', 'Spaceballs', 'Alien']
//                  0              1             2           3           4
removedMovies = movies.splice(0, 3)
// removedMovies is ['Caddyshack', 'Interstellar', 'Scarface']
// movies is [ 'Spaceballs', 'Alien' ]
//                  0           1
removedMovies = movies.splice(1, 0, 'The Sting')
// removedMovies is []
// movies is [ 'Spaceballs', 'The Sting', 'Alien' ]
//                  0              1         2
```

The `splice()` method always returns an array containing the removed elements.

### Add/Remove Elements To/From Anywhere in the Array

The `splice()` method is capable of **adding and/or removing** any number of elements inside an array with a single line of code!

If we check [the splice docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) we'll find the syntax to be:

```js
splice(start)
splice(start, deleteCount)
splice(start, deleteCount, item0)
splice(start, deleteCount, item0, item1)
splice(start, deleteCount, item0, item1, /* …, */ itemN)
```

This syntax list may seem overwhelming and confusing at first glance, but what it means is that all but the first parameter is optional - so when we call `splice()`, its behavior will change depending on how many arguments we pass to it. Let's explore this idea more.

#### Using `splice()` to Remove Element(s)

```js
// Remove 'Caddyshack' & 'Interstellar'
let removedMovies = movies.splice(1, 2);
// movies -> ['Jurassic Park', 'Contact']
// removedMovies -> ['Caddyshack', 'Interstellar']
```

#### Using `splice()` to Insert Element(s)

```js
// Insert 'Spaceballs' & 'Alien' after 'Jurassic Park'
removedMovies = movies.splice(1, 0, 'Spaceballs', 'Alien');
// movies -> ['Jurassic Park', 'Spaceballs', 'Alien', 'Contact']
// removedMovies -> [] (empty array)
```

#### Using `splice()` to Replace Element(s)

```js
// Replace 'Jurassic Park' & 'Spaceballs' with 'Best In Show'
removedMovies = movies.splice(0, 2, 'Best In Show');
// movies -> ['Best In Show', 'Alien', 'Contact']
// removedMovies -> ['Jurassic Park', 'Spaceballs']
```

As you saw, the `splice` method always returns an array containing the removed elements (an empty array if no elements were removed).

### 👉 You Do: Use `splice()` (1 min)

Here's my current `movies` array:

```js
movies //-> ['Best In Show', 'Alien', 'Contact']
```

- Use `splice()` to **replace** 'Contact' with 'The Matrix' & 'Gladiator'

Afterwards, this will be the `movies` array:

```js
movies //-> ['Best In Show', 'Alien', 'The Matrix', 'Gladiator']
```
