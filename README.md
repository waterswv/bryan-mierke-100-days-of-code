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