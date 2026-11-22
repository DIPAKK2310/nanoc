# nanoc

A tiny compiler written in JavaScript that turns Lisp-style function calls
into C-style function calls.

```lisp
(add 2 (subtract 4 2))
```
↓
```c
add(2, subtract(4, 2));
```

**Live demo:** <link to playground>

## Why I built this
One or two sentences: to learn how compilers work (tokenizing, parsing,
AST transformation, code generation). Credit the inspiration:
"Based on the ideas from the-super-tiny-compiler by Jamie Kyle."

## How it works
Source → Tokenizer → Parser → Transformer → Generator → Output

| Stage | File | What it does |
|-------|------|--------------|
| Tokenizer | src/tokenizer.js | Splits code into tokens |
| Parser | src/parser.js | Builds an AST |
| Transformer | src/transformer.js | Converts to target AST |
| Generator | src/generator.js | Prints the output code |

## Usage
```js
import { compile } from './src/index.js';
console.log(compile('(add 2 2)')); // add(2, 2);
```

## Features
- Numbers, strings, nested calls
- Error messages with line/column
- (your extras here)

## Run tests
```bash
npm test
```

## What I learned / Future ideas
- Short bullet list
- e.g. variables, operators, a different target language

## License
MIT