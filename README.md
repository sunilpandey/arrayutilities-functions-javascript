# Array Utilities Functions
Javascript provides many build in function to perform simple to complex operations in a one shot. Ideally we should use those functions instead of writing code for the same from scratch. This page is going to talk about those functions and usage of them.

## Finding Min/Max of a number array
Many times we hit into such situations when we need to find the min or max of an array. Javascript provides math functions to achieve these operation in one go
```typescript
const numbers = [1, 2, 3, 4];

// Finding max
const minValue = Math.min(...numbers);

// Finding min
const maxValue = Math.max(...numbers);

console.log(`Minimum value: ${minValue} Maximum value: ${maxValue}`);
```

## Combining two array
Some times we run into a problem where we need to combine two arrays into one.

Consider following array
```typescript
const numbers1 = [1, 2, 3 , 4];
const numbers2 = [5, 6, 7, 8];

// Using spread operators
let numbers12 = [...numbers1, ...numbers2];
console.log("Combined Arrays is: ", numbers12);

// Using concat method
numbers12 = numbers1.concat(numbers2)
console.log("Combined Arrays is: ", numbers12);

```

Both the upper technique will merge two array and generate different array. We may often need to merge one array into another. Such kind of operations can be performed using `push` and `splice` methods

### `push` method
Push methods are usefull when you have to merge another array into one only at last.
```typescript
const numbers1 = [1, 2, 3 , 4];
const numbers2 = [5, 6, 7, 8];
numbers1.push(...numbers2);

console.log(`numbers1 after number2 got merged ${numbers1}`);
```

### `splice` method
Splice method is location based merge. You can merge entire array from a specified location. 
Let suppose we need to merge the numbers1 array into to number2 but it should be at starting position 1 to keep it sorted.
```typescript
const numbers1 = [2, 3, 4, 5];
const numbers2 = [1, 6, 7, 8];
```

We can do that using splice method like below
```typescript
const insertLocation = 1;
const deleteCount = 0;

numbers2.splice(insertLocation, deleteCount, ...numbers1); 

console.log(`numbers2 after number1 got merged on location ${insertLocation}: ${numbers1}`);


