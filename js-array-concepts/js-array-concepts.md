# JS Arrays - Concepts

![JS array concepts hero image](./assets/js-arrays-concepts.png)

## What are arrays?

Think of arrays in JavaScript as a bookshelf full of books. Each book on the shelf is an element of the array. Books on the shelf have a specific order - there is a first book on the shelf and a last book on the shelf, and every book between has a specific location on the shelf.

Arrays can contain zero or more items called - *elements* (not to be confused with HTML elements). These elements are stored in a specific order. 

Each element in an array can hold any data type - strings, numbers, objects, functions, even other arrays. This sets JavaScript apart from many other programming languages. However, just because you can doesn't necessarily mean that you should - you'll see as we work with arrays we will typically want them to contain a single type of data.

In JavaScript, arrays are able to grow and shrink in size dynamically, and you're able to add to them without being concerned about their capacity.

Although it's common to refer to an array as its own data type, they are technically a subtype of the `Object` type. This means arrays are technically objects in JavaScript.

___
📚 An *element* in an array is an individual item stored at a specific position within an array. 
___

## Why use arrays?

Arrays are typically the data structure of choice for holding an ordered list of data. Imagine you wanted to record the high temperature in your location every day for a year. Without arrays, you would need to create a separate variable for each day that you collected a new piece of data. Instead, because we have arrays, we're able to store all of that temperature data in a single container.

Collecting that data in a single container has other benefits as well. Because all the high temperature data you've collected is held in one place, it's easier to carry out operations on that data - for example finding the average high temperature, or even the hottest or coldest day of the year.

As demonstrated by the example above, the real-world problems you'll solve often deal with collections of things. Arrays provide a natural way to model those collections in code.

___
📚 An *array* is a collection of items called elements stored in a specific order. Think of an array like a list or a container that holds multiple values.
___
