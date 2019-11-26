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