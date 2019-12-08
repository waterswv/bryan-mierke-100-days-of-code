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