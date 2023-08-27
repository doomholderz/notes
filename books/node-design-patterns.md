# Node.js Design Patterns

## Module Definition Patterns

Named exports: ./logger.js: exports.info = () => {} can be called as const logger = require("./logger"); logger.info("")

Class exports: class Logger {constructor (name) { this.name = name}}; module.exports Logger can be called as const logger = require("./logger"); const dbLogger = 
new Logger("db")

## ESM

No code is executed in ESM until dependency graph has been fully built

Module resolution phases:

1. Parsing: explored beginning at entry point, depth-first search into imported modules (each module visited only once)
2. Instantiation: interpreter walks from bottom to top of parsing tree, building out map of exports
3. Evaluation: code in each file is executed, from bottom to top (so last is entry point)

## Callback Pattern

Should be upfront about whether a function is synchronous or asynchronous, 
and use appropriate functions within to ensure this remains (e.g. 
readFileSync for a synchronous function)

We should use direct style (no callback functions) when writing 
synchronous functions.

When forced to use synchronous I/O functions, we should aim to make use of 
caches to prevent long drawn out I/O (though this only works when files 
are repeatedly read, otherwise we're still blocking the event loop every 
time the function is invoked)

In general, we use asynchronous I/O 

Can guarantee a callback is invoked asynchronously via process.nextTick()

Callback convention is the first argument of the callback is the error, 
and then the data. If no error, first argument should be null
