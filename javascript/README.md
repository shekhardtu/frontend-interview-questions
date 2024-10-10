
##### 1. Write poly-fill of the followings (Minimal Implementation) 
> - Bind: <https://gist.github.com/shekhardtu/1eded01d275e2dd9b089f2886ff9d9df>
> - Reduce: <https://gist.github.com/shekhardtu/80425b082e99fb2aa6270d436e8bbeaa>
> - Filter: <https://gist.github.com/shekhardtu/f782ecc4c33898579652919cd50b28d1>
> - Map: <https://gist.github.com/shekhardtu/19272c865ccdce8359d20579678c1f4d>
> - Some: <https://gist.github.com/shekhardtu/355acf3c8e5847c7057a78d3d22c8d1b>
> - Every: <https://gist.github.com/shekhardtu/a3c9be0ead9f0b20cae268709c32e8ed>
> - ForEach: <https://gist.github.com/shekhardtu/1c2ed226b191e512824f392f0e31d50d>
> - Promise.all: <https://gist.github.com/shekhardtu/79c193ff58f76e2abacf752ae4780775/>
> - Object.assign: <https://gist.github.com/shekhardtu/0f4539344c28f81613a7b0ab6d12d287>
> - Promise: <https://gist.github.com/shekhardtu/0f478b19cacaef66f6a01aaa041b8941>


##### 2. Explain and write standard functions of the followings
> - Debounce: <https://davidwalsh.name/javascript-debounce-function>
> - Throttle: <https://css-tricks.com/debouncing-throttling-explained-examples/>
> - Memomize: <https://www.freecodecamp.org/news/understanding-memoize-in-javascript-51d07d19430e/>
> - Object Deep Clone: <https://gist.github.com/shekhardtu/28247be45237a592cdfd7e858b92372d>

	
	
	
##### 3. Implement Design pattern of the followings
> - Singleton: <https://gist.github.com/shekhardtu/4cbf9e1e1e8598870e9e04f813c50a15>
> - Prototype: <https://dev.to/arnas/prototype-design-pattern--2lg2>
> - Pub/Sub: <https://jarrettmeyer.com/2016/04/18/observer-pattern-in-javascript>
> - Revealing module pattern: <https://scotch.io/bar-talk/4-javascript-design-patterns-you-should-know>
	
##### 4. Design a library or component / frontend assignment / live coding/ machine coding round
> - How to build a library: <https://www.erikschierboom.com/2015/08/05/building-a-javascript-library/>
> - Carousel: <https://codepen.io/shekhardtu/pen/eobMVW?editors=1010>
> - Auto-complete/Auto Suggest: [JavaScript] <https://codesandbox.io/s/focused-swartz-qhjxdn?file=/src/index.js>
> - Auto-complete/Auto Suggest:	[React] <https://codesandbox.io/s/autocomplete-autosuggest-in-reactjs-11vpqd?file=/src/App.js>
> - Trello: <https://codepen.io/shekhardtu/pen/eYOPJNg>
> - Splitwise 
> - Lazy loading
> - Modal/Popup: <https://codesandbox.io/s/unruffled-jasper-tm7cwp?file=/src/App.js>
> - Drag and Drop: <https://codesandbox.io/s/drag-and-drop-in-vuejs-96tmg4>
> - facebook like/comment module and reply to comment: <https://codepen.io/shekhardtu/pen/gJMOpL?editors=0010>
> - Simple Calender: <https://medium.com/@nitinpatel_20236/challenge-of-building-a-calendar-with-pure-javascript-a86f1303267d>
> - Autosuggest multiple tags: <https://codepen.io/shekhardtu/pen/ymzXgv>
> - Progress bar: <https://codepen.io/shekhardtu/pen/ROEJyx?editors=0010>
		  <https://codepen.io/shekhardtu/pen/ZEzRVpx>
		  
	

##### 4. Explain prototypal inheritance with some example 
> - <https://codeburst.io/master-javascript-prototypes-inheritance-d0a9a5a75c4e>
> - <https://javascript.info/prototype-inheritance>

##### 5. Memory leaks in closures? Where closure variable are stored?
> - <https://www.lambdatest.com/blog/eradicating-memory-leaks-in-javascript/>
> - <https://auth0.com/blog/four-types-of-leaks-in-your-javascript-code-and-how-to-get-rid-of-them/>
> - <https://stackoverflow.com/questions/19550253/memory-leaks-and-closures-in-javascript-when-and-why>

##### 6. Implement jQuery, underscore like library?
> - <https://www.freecodecamp.org/news/how-to-write-a-jquery-like-library-in-71-lines-of-code-learn-about-the-dom-e9fb99dbc8d2/>
> - <https://gomakethings.com/how-to-create-your-own-vanilla-js-dom-manipulation-library-like-jquery/>

##### 7. Implement curry function:

```js
var temp = curry(avg, 1, 2, 3);
temp(10); //4 - stores 1, 2, 3 in closures and adds 10 for average
temp(1, 2); //1.8 - stores 1, 2, 3 in closures and add 1, 2 for average

//Average function:
var avg = function (...param) {
    var sum = 0;
    for(var i = 0; i < param.length; i++) {
        sum += param[i];
    }
    return param.length > 0 ? sum / param.length : 0;
}

var curry = function (fn, ...m) {
    return function (...n) {
        return fn.apply(this, m.concat(n));
    }
}

```
##### 8. What new does when we create instance, what if we do not add it etc.
> - <https://javascript.info/constructor-new>

##### 9. Difference between classical and prototype inheritence? If you design a language, which one will you choose?
> - <https://medium.com/javascript-scene/master-the-javascript-interview-what-s-the-difference-between-class-prototypal-inheritance-e4cd0a7562e9>
> - <https://dev.to/crishanks/classical-vs-prototypal-inheritance-2o5a>

##### 10. Testing framework in detail - How will you test ajax request, fixtures, mocking, spy, stub etc.
To test AJAX requests, you can use a combination of testing frameworks and libraries like:

Jest for unit testing
Sinon.js for spies, stubs, and mocks
nock or fetch-mock to mock HTTP requests For example:
Spy: Tracks calls made to a function.
Stub: Replaces a function to control its behavior in a test.
Mock: Simulates external services or APIs. For AJAX requests, use a library like axios or fetch. To mock AJAX requests, use fetch-mock to simulate API responses.
js

```javascript
import fetchMock from 'fetch-mock';
import { getData } from './api'; // Your function making API call

test('fetches data successfully', async () => {
  fetchMock.get('https://api.example.com/data', { data: [1, 2, 3] });

  const response = await getData();
  expect(response.data).toEqual([1, 2, 3]);

  fetchMock.restore();
});
```

##### 11. Why immutability is important? How will you bring immutability in JS?
> - <https://stackoverflow.com/questions/34385243/why-is-immutability-so-important-or-needed-in-javascript>

##### 12. const obj = { "a" : 1 }, Can I change obj.a and why can I change it if const means that variable cannot be reassigned or re-declared?
Yes, you can change obj.a. The const keyword prevents reassignment of the obj variable itself, but the contents (properties) of the object can still be modified. In JavaScript, const does not create immutable objects, only immutable references.

```js

const obj = { a: 1 };
obj.a = 2; // This works because you're not reassigning the object, only changing a property
```

##### 13. Object.freeze and Object.seal. Another way of asking is, how will you prevent object property value to be updated or added?
Object.freeze(obj): Prevents any modifications to the properties and values of an object. The object becomes fully immutable.
Object.seal(obj): Prevents new properties from being added or deleted but allows modifications to existing properties.
```js
Copy code
const obj = { a: 1 };
Object.freeze(obj);
obj.a = 2; // No effect, obj.a remains 1
```

##### 14. Event loop in JavaScript
> - <https://gist.github.com/shekhardtu/f7c948be9090b760556639031a5818e1>

##### 15. In what order will the numbers 1-4 be logged to the console when the code below is executed? Why?

```js
(function() {
    console.log(1); 
    setTimeout(function(){console.log(2)}, 1000); 
    setTimeout(function(){console.log(3)}, 0); 
    console.log(4);
})();
```

##### 16. What is the output out of the following code? Explain your answer.
```js
var a={},
    b={key:'b'},
    c={key:'c'};

a[b]=123;
a[c]=456;

console.log(a[b]);
```

##### 17. Difference and uses of Callback, Promise, Observable, Generators 
> - <https://medium.com/@RupaniChirag/promises-generators-and-observable-in-javascript-9f09bde7528e>

##### 18. Design a game eg. tic tac toe etc.
##### 19. How can I get the depth of the deepest li tag in an unordered list?
> - <http://stackoverflow.com/questions/22248432/calculate-depth-of-unordered-list>

##### 20. How will you do dfs in html nodes?
> - <https://stackoverflow.com/questions/39503861/javascript-only-dom-tree-traversal-dfs-and-bfs>

##### 21. Write a function to get factorial and cache the result. If it's called next time, return from cache. 
       a. How can you improve the performance of factorial using memoization?      
       b. How can you improve memoization approach since it takes more space?
       c. We can ask which one is better recursive or iterative version of factorial?
    
##### 22. lib.add(10).sub(20).mul(2).div(1) - Implement a function with use of closure
##### 23. How will you handle cross site scripting, sanitization etc.?
##### 24. How will you handle date - time in your product?
##### 25. What is Cross-site request forgery(CSRF) and How will you save site from Cross-site request forgery?
	https://www.freecodecamp.org/news/a-quick-introduction-to-web-security-f90beaf4dd41/
CSRF is an attack where an unauthorized command is transmitted from a user that the website trusts. It exploits the trust that a site has in a user's browser.
Protection methods:
CSRF Tokens: Generate unique tokens for each user session and validate them with every state-changing request.
SameSite cookies: Setting cookies with the SameSite flag helps mitigate CSRF attacks.
Double Submit Cookies: Sending CSRF tokens in both cookies and request headers.

##### 26. How declare static variable and function and what's the use?
##### 27. What will be output of below:
```js
X = [1,2];
X.push(X);
console.log(X);
```
Output: [1, 2, Array(3)] Explanation: The push method adds the reference of the array X to itself, so the array includes itself as an element. If you attempt to access the third element (X[2]), it will point back to the entire array X, leading to circular references.

##### 28. How will you replace backslash in a string? 
##### 29. What and why will be output of following:
```js
var a = '1';
var b = 'c';
console.log(a + b); //1c
console.log(a - b); //NaN
console.log(a * b); //NaN
console.log(a / b); //NaN

var a = 1;
var b = '2';
console.log(a + b); //12 
console.log(a - b); //-1
console.log(a * b); //2
console.log(a / b); //.5
```
##### 30. JavaScript is pass by value or pass by reference? 
//Primitive type (string, number, etc.) are passed by value and objects are passed by reference
###### 31. What is the output of following? What is the reason for output, how many closures are created in following example?
```js
for(var i = 1; i <= 5; i++) {
    setTimeout(function () {
        console.log(i);
     }, 1000*i);
    
}

Fix:

for(var i = 1; i <= 5; i++) {
    (function (i) {
        setTimeout(function () {
            console.log(i);
        }, 1000*i);
    })(i);
}

another fix
for(let i = 1; i <= 5; i++) {
   setTimeout(function () {
     console.log(i);
    }, 1000*i);
}
```
##### 32. Output of following
```js
(function() {
    x = 1;
    function x() {};
    var x;
    console.log('var x => ', x);	
})()
```
hositing order => funtion definition -> variable declaration 
##### 33. Question on static function:
```js
function A() {}
// Static
A.getSmth = function() {
	return 1;
}
// Public
A.prototype.getAnother = function() {
	return 2;
}

var a = new A();
try {
	console.log(a.getSmth());
} catch(e) {
	console.log('a.getSmth() TypeError => ', e.constructor.name);
}
```

##### 34. Output of following:
```js
var head = {};
    var newNode = {};
    head.next = newNode;
    newNode.next = head;
    head = null;
    console.log('newNode.next => ', newNode.next);
```
##### 35. Difference between reflow and repaint? How to avoid it? What is RequestAnimationFrame?
Reflow: Occurs when the browser calculates the layout of part or all of the page. Changes in DOM structure or size triggers a reflow.
Repaint: Occurs when visual parts of the page (e.g., color) change without affecting layout.
Avoiding reflow/repaint:
Minimize DOM manipulations.
Use visibility: hidden instead of display: none (as display: none triggers reflow).
Batch DOM updates (e.g., using DocumentFragment).
requestAnimationFrame: It synchronizes your code execution with the browser's repaint cycle for smooth animations.
```js
function animate() {
  // Animation logic
  requestAnimationFrame(animate);
}
requestAnimationFrame(animate);
```
	
##### 36. How to handle images in responsive website - srcset, sizes, base64, blurring effect using canvas etc.

##### 37. Server side rendering vs client side rendering and its effect on SEO and performence

##### 38. Progressive Web App: Create a dummy app of weather report

##### 39. All type of ajax request, headers, options call, CORS etc.

##### 40. Implementation and difference between Two way data binding vs one way data binding

##### 41. OAuth implementation

##### 42. CSS 3.0 - Animation and other props

##### 43. Chrome dev tool - e.g. profiler etc.


##### 45. Implementation of state management in react

##### 46. Implement generic curry function:
```js
function getVolume(l, h, w) {
	console.log('voulume: ' + (l * h * w));
}

function curryFun(fn) {
	var arrLength = fn.length;
	return (function repeat() {
		var mem = [].slice.apply(arguments);
		return function() {
			var next = mem.concat([].slice.apply(arguments));
			return next.length >= arrLength ? fn.apply(null, next) : repeat.apply(null, next);
		}
	}());
}

var curry = curryFun(getVolume);

curry(2)(3)(4);
```
##### 47. CSS Questions - Box Model (margin-collapse rules, box-sizing),
	float (clear etc., effect of display: block),
	position, overflow-hidden: what it does,
	Ways to align the item center,
        flex box, grid layout, box-shadow
##### 48. setInterval and clearInterval using setTimeout and clearTimeout
You can create a custom setInterval using setTimeout like this:

```js
function customSetInterval(fn, delay) {
  let intervalId;

  function repeat() {
    fn();
    intervalId = setTimeout(repeat, delay);
  }

  intervalId = setTimeout(repeat, delay);
  return {
    clear() {
      clearTimeout(intervalId);
    }
  };
}

const interval = customSetInterval(() => console.log('Running...'), 1000);

// To clear the interval after some time
setTimeout(() => interval.clear(), 5000);
```

##### 49. CSS Interview questions: https://css-tricks.com/interview-questions-css/
##### 50. Write a curry function to execute the following questions

```js
function curry(fn) {
    if(fn.length === 0) {
        return fn.apply();
    }
    function nest(N, args) {
        return function() {
            var arg = [].slice.apply(arguments);
            if(N - arg.length <= 0) {
                return fn.apply(null, args.concat(arg));
            }
            args = args.concat(arg);
            return nest(N - args.length, args);
        }
    }
    return nest(fn.length, []);
}

var sum = function (x, y, z) {
    return x + y + z;
}

var result = curry(sum);
console.log(result(1)(2)(3));
console.log(result(1, 2)(3));
console.log(result(1)(2, 3));
```

##### 54. Difference between get, post, put, delete
##### 55. How to use Memoize to cache JavaScript function results and speed up your code 
<https://medium.freecodecamp.org/understanding-memoize-in-javascript-51d07d19430e>
##### 56. How can I display just a portion of an image in HTML/CSS?
<https://stackoverflow.com/questions/57725/how-can-i-display-just-a-portion-of-an-image-in-html-css>

##### 57. Middelware design pattern: https://gist.github.com/darrenscerri/5c3b3dcbe4d370435cfa
##### 59. Web components, npm modules 
##### 60. Write a function to evaluate 
> - add(1)(2)(3);
> - add(1)(2,3)(4)(5,6,7);
> - add(2,3,4,5)(1)();
> - add(20)(10)(10).toValue();
> - Solution: <https://gist.github.com/shekhardtu/b7f3e618f2fd225e1a3a6d9d19f8c708>>
##### 61. Explain different type of web caching  
##### 62. Difference between http, https and http2 protocols 
##### 63. What is tail call optimization
> - <https://hackernoon.com/es6-tail-call-optimization-43f545d2f68b>


##### Few articles to brush up js interview questions
> - <https://dev.to/aershov24/top-26-javascript-interview-questions-i-wish-i-knew-26k1>
> - <https://dev.to/adyngom/28-relevant-javascript-interview-questions-part-i-the-first-4-2a16>
> - <https://dev.to/adyngom/4-more-relevant-javascript-questions-to-help-fix-the-broken-coding-interview-3b8k>
> - <https://www.freecodecamp.org/news/cracking-the-front-end-interview-9a34cd46237/>
> - <https://medium.com/@nabendu82/interview-preparation-basic-javascript-1-3003b0ac3832>
> - <https://medium.com/@nabendu82/interview-preparation-basic-javascript-2-ad71d09eb0af>
> - <https://scotch.io/courses/10-need-to-know-javascript-concepts/the-this-keyword>
