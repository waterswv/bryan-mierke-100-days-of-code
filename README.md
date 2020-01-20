# Bryan Mierke | 100 Days of Code | Doing Node

## Table of Contents
* Days
* Details
* Code Samples
* Background
* Big Milestones

## Days
1. Day 1 | 11/20/19 | Node Error Types
2. Day 2 | 11/21/19 | Node REPL & Setup socket connection
3. Day 3 | 11/22/19 | 4 Types of Streams & EventEmitters
4. Day 4 | 11/23/19 | Rate of Growth & Big O Notation
5. Day 5 | 11/24/19 | Binary Search Tree Run time
6. Day 6 | 11/25/19 | Array.keys()
7. Day 7 | 11/26/19 | RegExp with test() & match()
8. Day 8 | 11/27/19 | Diff ways to create a Closure
9. Day 9 | 12/02/19 | jQuery Data Fetching in React
10. Day 10 | 12/03/19 | Arrow Functions & this
11. Day 11 | 12/04/19 | Self signing ssl certs
12. Day 12 | 12/05/19 | SVG defs and patterns
13. Day 13 | 12/05/19 | Catch up day - Rename variable during destructuring
14. Day 14 | 12/06/19 | Flip values with destructuring
15. Day 15 | 12/07/19 | Promise Error Handling
16. Day 16 | 12/08/19 | Array.from()
17. Day 17 | 12/09/19 | For...of w/ destructuring
18. Day 18 | 12/10/19 | Node querystring module
19. Day 19 | 12/11/19 | Custom node querystring seperator & assingment
20. Day 20 | 12/12/19 | Find the smallest value in an object
21. Day 21 | 12/13/19 | Symbols
22. Day 22 | 12/14/19 | Iterator
...
23. Day 23 | 12/15/19 | Generator
24. Day 24 | 12/16/19 | Lodash deepClone
25. Day 25 | 12/17/19 | private & readonly class
26. Day 26 | 12/18/19 | .zshrc setup
27. Day 27 | 12/19/19 | .npmrc file
28. Day 28 | 12/20/19 | using nvm
29. Day 29 | 12/21/19 | using ssh with git
30. Day 30 | 12/22/19 | Angular CLI setup
31. Day 31 | 12/23/19 | ng generate component
--. Day -- | 12/24/19 | Holiday
--. Day -- | 12/25/19 | Holiday
32. Day 32 | 12/26/19 | Angular directive
33. Day 33 | 12/27/19 | Function decorator
34. Day 34 | 12/28/19 | typescript class
35. Day 35 | 12/29/19 | typescript implements
36. Day 36 | 12/30/19 | typescript instanceOf
37. Day 37 | 12/31/19 | Using artifactory
--. Day -- | 1/1/20 | Holiday
38. Day 38 | 1/2/20 | Generator Function
39. Day 39 | 1/3/20 | Observable in Angular
40. Day 40 | 1/4/20 | Pipe in RXjs
41. Day 41 | 1/5/20 | Map in RXjs
42. Day 42 | 1/6/20 | WeakMap
43. Day 43 | 1/7/20 | Get & Set methods
44. Day 44 | 1/8/20 | Angular component example
45. Day 45 | 1/9/20 | Angular service example
46. Day 46 | 1/10/20 | CSS Breakword property
47. Day 47 | 1/11/20 | Lodash concat
48. Day 48 | 1/12/20 | Lodash merge
49. Day 49 | 1/13/20 | Lodash keys
50. Day 50 | 1/14/20 | Constructors
51. Day 51 | 1/15/20 | Switch case with costructors
52. Day 52 | 1/16/20 | Subclasses
53. Day 53 | 1/17/20 | Basic ngrx reducer
54. Day 54 | 1/18/20 | ngrx selector
55. Day 55 | 1/19/20 | Subject Observable




## Details

**Day 1** ... Did you know that node has 4 main Error contexts & 2 main types?
* **Contexts** 
⋅⋅⋅ *Synchronous* ⋅⋅⋅ *Asynchronous* ⋅⋅⋅ *Event* ⋅⋅⋅ *Promise*
1. **Errors**: A non fatal condition that can be caught and handled typcially with error 1st callback pattern
2. **Exceptions**: A serious error that a sane environment should not ignore or try to handle i.e. Trigger process restart

**Day 2** ... Node has a native REPL, but you can also create your own instance
i.e. To open the native REPL run `node` in your terminal.
Or you can also setup your own repl using the repl & net Node apis. See the Day 2 code samples for a client & server socket connection running an interactive repl on port 8080.

**Day 3** Node Streams & EventEmitters

**Day 4** Algorithm efficiency & Big O Notation

See my gist on run time and algorithm effieciency [HERE](https://gist.github.com/waterswv/b4b028071867b43f196b3bd8e105848f)

Helpful [Stackoverflow](https://stackoverflow.com/questions/1592649/examples-of-algorithms-which-has-o1-on-log-n-and-olog-n-complexities) examples of algorithm run times.

**Day 5** Binary Search Tree 
> For the most your binary search tree should have a run-time of O( log n), this is because if we are searching through an array of size n, and halving the array each time time until we get the value we want, that can be expressed as base-2 logarithm of n, AKA O(log n). Logarithm functions grow very slowly and are the inverse of exponentials, which grow very quickly. Worse case scenario you have a lot of values, the run-time is usually O(n).

Ref: [Article](https://medium.com/killingmeswiftly/binary-search-tree-18491204c281)

**Day 6** Array.keys() function returns an array of position keys for an array regardless if the value of an array is undefined or has been deleted. Unlike Object.keys() which will omit positions keys if the value is undefined.

**Day 7** RegExp - you can create as a literal or with new Constructor object. Utilize test() on the regex or you can use match() on the variable. Test will return a boolean while match will return null or an array of the matches.
See code sample for example of both.

**Day 8** Create a closure with a block of code to lock variables in their execution instances. When using var it's necessary to use patterns, like currying, to ensure variables are locked within their block. Additionally you can use `let` or `const` to make things easier as their es6 syntax works to implement a block scope. `See code sample`

**Day 9** Had to use jQuery in a live code interview recently. Made a codesandbox to refresh on Promises on how I fetched data with jQuery in React. 'Synchronous' vers, Async/Await, and Promises implementation. [Code Sandbox](https://codesandbox.io/s/awesome-sun-1wgkb?fontsize=14&hidenavigation=1&theme=dark)

**Day 10** Arrow functions & this. If you need to access the *this* object within a callback or function scope; Make sure you use a function () { } block instead of an arrow function () => {}. Arrow functions just inherit *this* from their parent block as they do not rebind on execution. Code sample below.

**Day 11** Self-signed SSL cert for Development & serving over *https*
As a practice we should always use SSL connections. To achieve this practice we can use the following code to create a self-signed cert so we can use the node HTTPS module durving dev; just be aware it doesn't demonstrate identity. 

**Day 12** SVG is Cool. HTML5 svg elements allow you to define a pattern and then use that pattern to fill an entire shape! `<defs> <pattern> <circle>` Code sample below. Ref: [MDN Example](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/pattern)

**Day 13** Object destructuring in JS is a cool feature. Quickly access obj variables `const { name, age } = person`. You can even rename the variables in the event you want to be more specific or change details. i.e. `const { name: firstName, age } = person` Where name has been changed to firstName!

**Day 14** You can flip 2 values in an array with destructuring. [ val1, val2 ] = [ val2, val1 ] ... val1 is now val2

**Day 15** Promise Error hndling can use single catch i.e. then().then().catch() but if you want to continue chain you need a catch() after each then() since errors cause every subsequent then() block 2 be skipped until catch block occurs.

**Day 16** Array.from() can be used to convert any set of items, nodes, dom element NodeList into an array. `const newArray = Array.from(document.querySelectorAll('div'))` 

**Day 17** a for...of loop will provide you with every item in an array without the clunky index intiatlizing and length count. If you need to grab the index then you can use Array.prototype.entries() and destructure the index and value during loop definition as it creats an iterable. `for(const [idx, item] of items.entries()){ ... }`

**Day 18** Nodes querystring module has a parse & stringify method to generate a key:value pair object from a qrystr & vice versa respectively. `querystring.parse(search=food&limit=5) // results in {search: food, limit: 5}`

**Day 19** Continuing with nodes qs module. You can have custom separator and assignment args passed respectively 2nd and 3rd. i.e. querystring.parse('search:food%limit:5%offset:2', '%', ':')

**Day 20** Use reduce to find the smallest value in an object. Use Object.keys(Your_Obj_Variable) to grab the keys then pass in the object & keys to a reduce function. Code sample below.


## Code Samples

**Day 2:**

` // Client `
```
let net = require('net')
let sock = net.connect(8080)

process.stdin.pipe(sock)

sock.pipe(process.stdout)
```
`// Server`
```
let repl = require('repl')
let net = require('net')

net.createServer(socket => {
  repl
    .start({
      prompt: 'Socket:8080 > ',
      input: socket,
      output: socket,
      terminal: true
    }).on('exit', () => {
      socket.end()
    })
}).listen(8080, port => console.log('Server listeining on port 8080'))
```

**Day 7**
```
// Random string variables

let str = 'hi there friend, its nice to meet you friend'
let str2 = 'ah0 yes'

// 2 identical RegExp variables that check to NOT include numbers
const check2 = /^([^0-9]*)$/
const rCheck = new RegExp(/^([^0-9]*)$/)

// Match is used on a variable to test and passing regex as variable.
// Returns Null if false ... Array of matches if true
str.match(check2)

// test can only be performed on regex passing in variable to check ... will return boolean
rCheck.test(str2)
```

**Day 8**
```
// Test array for our closure loops
const arr = ['a', 'b', 'c', 'd']

// This loop will spit out 4 and undefined 4 times.

for(var i = 0; i < arr.length; i++){
	setTimeout(function() {
		console.log('The index is ' + i + ' and arr value is ' + arr[i])
	}, 2000)
}

// Closure created around a var variable ... this will work

for(var i = 0; i < arr.length; i++){
	(function timer(i) {
		setTimeout(function() {
		  console.log('The index is ' + i + ' and arr value is ' + arr[i])
		}, 2000)
	})(i)		
}
	
// closure created with let block scoping index ... this will work
  
for(let i = 0; i < arr.length; i++){
	setTimeout(function() {
	  console.log('V2 The index is ' + i + ' and arr value is ' + arr[i])
	}, 2000)		
}

// closure created by using let within loop ... this will work
	
for(var i = 0; i < arr.length; i++){
	let idx = i
	setTimeout(function() {
		console.log('V3 The index is ' + idx + ' and arr value is ' + arr[idx])
	}, 2000)
}
```

**Day 10**
```
// Correct
 item.addEventListener('click', function() {
        let myClass = 'my-class'
        
        // Toggles on & off a class from the classes array
        this.classList.toggle(first)
 }
 // Incorrect
 item.addEventListener('click', () => {
        let myClass = 'my-class'
        
        // if this is placed within a script tag this would be bound to the Window Object
		// Arrow functions do not ReBind 'this'
        this.classList.toggle(first)
 }
```
**Day 11**
```
// Generate a Cert in the Terminal
openssl genrsa -out server-key.pem 2048
 openssl req -new -key server-key.pem -out server-csr.pem
 openssl x509 -req -in server-csr.pem -signkey server-key.pem -out server-cert.pem

// Using cert during server init
const https = require('https')
const fs = require('fs')

https.createServer({
	key: fs.readFileSync('server-key.pem'),
	cert: fs.readFileSync('server-cert.pem')
}, (req, res) => {
	// Any additional server funcs or config goes here
}).listen(443)
```

**Day 12**
```
    <div>
      <svg viewBox="0 0 230 100" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <pattern id="star" viewBox="0,0,10,10" width="10%" height="10%">
            <polygon points="0,0 2,5 0,10 5,8 10,10 8,5 10,0 5,2" />
          </pattern>
        </defs>

        <circle cx="50" cy="50" r="50" fill="url(#star)" />
   
      </svg>
    </div>
```
**Day 18**
```
const qs = require('querystring')

qs.parse('search=food&limit=5')
// returns a object { search: food, limit: 5 }

qs.stringify({
	search: food,
	limit: 5,
	offset: 2
})
// returns a string 'search=food&limit=5&offset=2'
```

**Day 19**
```
const qs = require('querystring')

// seperator is % instead of &
// assignment is : instead of =
qs.parse('search:food%limit:5%offset:2', '%', ':')

// returns a object { search: food, limit: 5, offset: 2 }


```
**Day 20**
```
function minimum (keys, obj) {
  return keys.reduce((acc, key) => {
    if (acc <= obj[key]) return acc
    return obj[key]
  }, undefined)
}
```