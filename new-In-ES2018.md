In this article, we will discuss about the new features in ECMA SCRIPT 2018 or ES9, including the examples of what they are and their use cases.  

Javascript is ever evolving language, we have seen the dramatic changes since the beginning of it inception to most recent mega release of ES6(ECMA SCRIPT 2015). 


### Asynchronous Iteration: 

You might have encountered with asynchronous iteration using async/await 
 
 ```js 
 async function performSomething(array) {
    for(var i = 0; i < array.length; i++) {
      await asyncRequest(array[i]) 
    }
  }
 ```
  
It will work but there is cleaner way to do it. ES9 has introduce asynchronous for loop iterators 
  
```js
async function performSomething(array) {
  for await(let i of array) {
     asyncRequest(array[i]) 
  }
}
```

### Promise.finally(); 

The promise object contains the set of asynchronous states. It can be either pending, success or failed. In promise we have
execute the success events using .then() method and failed in .catch() method. But their might be chances that we need to perform 
some tasks in either of the condition. ES9 has introduced the .finally prototype. You don't need to duplicate the code in then() or catch() 
write logic regard less of the state in .finally() method. 

```js
function doSomething() {
  doAnotherThing()
  .then()
  .then()
  .then()
  .catch()
  .finally(()=> {
    // Do all common things of then and catch state
   });
}
```

### Rest/Spread Operator for Objects as well as arrays

In ES6, javascript release the rest/spread operators with array. Similarly ES9 enables objects destructuring using rest/Spread operator. 

```js
const obj = {
a: 1,
b: 2, 
c: 3
}

const {a, ...b} = obj; 
// a = 1; b = { b: 2, c: 3}; 

```

Or you can use it to pass the param value similar to rest operator in Arrays

```js
const obj = {
a: 1,
b: 2, 
c: 3
}

function sum({a, ...b}) {
 // a = 1; 
 // b: {b: 2, c: 3}
}
```

You should remember, similar to the array rest param, you can only use one rest param at the end of the parameteres. 
In Object rest, it only works in the top level of object but not the nested properties of the object.

Spread operator can be used to copy one Object in another Object. 
```js
const obj1 = {a: 1, b: 2, c: 3};
const obj2 = {...obj2, d: 4, e: 5} // {a: 1, b: 2, c: 3, d: 4, e: 5}
```

*Note: while using Object spread operator, be aware that it will copy only immediate properties (shallow copies).* 



