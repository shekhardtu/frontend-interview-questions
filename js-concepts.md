##### 1. Write poly-fill of Object.create and explain why it worked

```js 
if(typeof Object.create != "function") {
    Object.create = function(param) {
        var Fun = function(){};
        Fun.prototype = param;
        return new Fun();
    }
}
```

##### 2. What new does when we create instance, what if we do not add it etc.
##### 3. Write poly-fill of bind and extend it to support following functionality:

```js
var obj = { x: 1, y: 2 };
function sum (arg1, arg2, arg3) {
    return this.x + this.y + arg1 + arg2 + arg3;
}

var myCaller = sum.bind(obj, 4);
myCaller(5, 6); //18 is the answer

Function.prototype.bind = function() {
    var arg = [].slice.call(arguments);
    var that = arg[0];
    var items = arg.slice(1);
    var self = this;
    return function () {
        var elements = Array.prototype.slice.call(arguments);
        return self.apply(that, items.concat(elements));
    }
}

```
##### 4. Implement curry function:
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
###### 5. Memory leaks in closures? Where closure variable are stored?
###### 6. Implement jQuery, underscore like library?
###### 7. Design a library or component - Carousel, auto-complete, game timer, split - wise, lazy loading etc.
###### 8. Implement Design pattern - Pub/Sub, Mixin, Observer, revealing module pattern?
###### 9. Difference between classical and prototype inheritence? If you design a language, which one will you choose?
###### 10. Testing framework in detail - How will you test ajax request, fixtures, mocking, spy, stub etc.
###### 11. Why immutability is important? How will you bring immutability in JS?
###### 12. const obj = { "a" : 1 }

###### Can I change obj.a and why can I change it if const means that variable cannot be reassigned or re-declared?

###### 13. Object.freeze and Object.seal. Another way of asking is, how will you prevent object property value to be updated or added?
###### 14. Event loop in JavaScript
###### 15. In what order will the numbers 1-4 be logged to the console when the code below is executed? Why?

(function() {
    console.log(1); 
    setTimeout(function(){console.log(2)}, 1000); 
    setTimeout(function(){console.log(3)}, 0); 
    console.log(4);
})();

###### 16. What is the output out of the following code? Explain your answer.

var a={},
    b={key:'b'},
    c={key:'c'};

a[b]=123;
a[c]=456;

console.log(a[b]);

###### 17. Callback, Promise, Observable, Generators 
###### 18. Design a game eg. tic tac toe etc.
###### 19. How can I get the depth of the deepest li tag in an unordered list?

http://stackoverflow.com/questions/22248432/calculate-depth-of-unordered-list

###### 20. How will you do dfs in html nodes?
###### 21. Write a function to get factorial and cache the result. If it's called next time, return from cache. 
       a. How can you improve the performance of factorial using memoization?      
       b. How can you improve memoization approach since it takes more space?
       c. We can ask which one is better recursive or iterative version of factorial?
    
###### 22. lib.add(10).sub(20).mul(2).div(1) - Implement a function with use of closure
###### 23. How will you handle cross site scripting, sanitization etc.?
###### 24. How will you handle date - time in your product?
###### 25. What is Cross-site request forgery(CSRF) and How will you save site from Cross-site request forgery?
###### 26. How declare static variable and function and what's the use?
###### 27. What will be output of below:

X = [1,2]
X.push(X)
console.log(X)

###### 28. How will you replace backslash in a string? 
###### 29. Wha will be output of following:

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

###### 30. JavaScript is pass by value or pass by reference? 
//Primitive type (string, number, etc.) are passed by value and objects are passed by reference
###### 31. What is the output of following? What is the reason for output, how many closures are created in following example?

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

###### 32. Output of following

(function() {
    x = 1;
    function x() {};
    var x;
    console.log('var x => ', x);	
})()

###### 33. Question on static function:

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


###### 34. Output of following:

var head = {};
    var newNode = {};
    head.next = newNode;
    newNode.next = head;
    head = null;
    console.log('newNode.next => ', newNode.next);

###### 35. Difference between reflow and repaint? How to avoid it? What is RequestAnimationFrame?
	
###### 36. How to handle images in responsive website - srcset, sizes, base64, blurring effect using canvas etc.

###### 37. Server side rendering vs client side rendering and its effect on SEO and performence

###### 38. Progressive Web App

###### 39. All type of ajax request, headers, options call, CORS etc.

###### 40. Two way data binding vs one way data binding

###### 41. OAuth implementation

###### 42. CSS 3.0 - Animation and other props

###### 43. Lazy loading implementation

###### 44. Chrome dev tool - e.g. profiler etc.

###### 45. How will you implement 2 way data binding

###### 46. debounce and throttle method

###### 47. Implementation of state management in react

###### 48. Implement generic curry function:

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

###### 49. CSS Questions - Box Model (margin-collapse rules, box-sizing),
	float (clear etc., effect of display: block),
	position, overflow-hidden: what it does,
	Ways to align the item center,
        flex box, grid layout, box-shadow
###### 50. setInterval and clearInterval using setTimeout and clearTimeout
###### 51. CSS Interview questions: https://css-tricks.com/interview-questions-css/
###### 52. function curry(fn) {
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

###### 53. Write Poly-fill of Promise? https://brunoscopelliti.com/lets-write-a-promise-polyfill/
###### 54. Difference between get, post, put, delete
###### 55. How to use Memoize to cache JavaScript function results and speed up your code 
https://medium.freecodecamp.org/understanding-memoize-in-javascript-51d07d19430e
###### 56. How can I display just a portion of an image in HTML/CSS?
https://stackoverflow.com/questions/57725/how-can-i-display-just-a-portion-of-an-image-in-html-css

###### 57. Middelware design pattern: https://gist.github.com/darrenscerri/5c3b3dcbe4d370435cfa
###### 58. Develop progress bar component
###### 59. Web components, npm modules 
