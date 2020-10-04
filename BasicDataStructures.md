Basic Data Structures: Iterate Through All an Array's Items Using For Loops

```Javascript
function filteredArray(arr, elem) {
  let newArr = [];
  // Only change code below this line
  for (let i = 0; i < arr.length; i++) {
    
    if ( arr[i].every (value => value !== elem )  ) 
    {
      
      newArr.push(arr[i]);
    }
  } 
  // Only change code above this line
  return newArr;
}

console.log(filteredArray([[3, 2, 3], [1, 6, 3], [3, 13, 26], [19, 3, 9]], 3));

 ``` 
 Basic Data Structures: Create complex multi-dimensional arrays

```Javascript 
let myNestedArray = [
  // Only change code below this line
  ['unshift', false, 1, 2, 3, 'complex', 'nested'], /// segundo nivel 
  [
    ['deep', 'shift', 6, 7, 1000, 'method'],  // terceiro nivel 
  ],
  [
    [
      ['deeper', false, true, 'spread', 'array'],///quarto nivel 
    ]
  ],
  [
    [
      [
        ['deepest', 1327.98, 'splice', 'slice', 'push'], /// quinto nivel 
      ]
    ]
  ],
  ['iterate', 1.3849, 7, '8.4876', 'arbitrary', 'depth']
  // Only change code above this line
];

``` 
Basic Data Structures: Add Key-Value Pairs to JavaScript Objects

```Javascript 
let foods = {
  apples: 25,
  oranges: 32,
  plums: 28
};

// Only change code below this line
foods.bananas = 13;
foods['grapes'] = 35;
const fruit = 'strawberries';
foods[fruit] = 27;
// Only change code above this line

console.log(foods);
``` 
Basic Data Structures: Modify an Object Nested Within an Object

```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 
```Javascript ``` 