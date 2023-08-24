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
