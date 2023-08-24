# JS Arrays - Manipulation

![JS arrays manipulation hero image](./assets/hero.png)

## Adding Elements to an Array

We can add elements to the **end** of an array using the [`push`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push) method:

```jsx
const movies = []
movies.push('Trading Places', 'Antitrust')
// movies is now ['Trading Places', 'Antitrust']
```

Note that more than one element can be added at a time.

We can also add to the **front** of an array with `unshift`:

```jsx
movies.unshift('Star Wars')
// movies is ['Star Wars', 'Trading Places', 'Antitrust']
```