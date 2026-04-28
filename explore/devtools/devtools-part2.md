# DevTools Part 2 - Debugging

## What was the bug?
The bug was in the `calculateSum()` function in `explore.js`. On line 9, `num1` and `num2` are obtained from `document.getElementById().value`, which always returns a string. So when the code does `let result = num1 + num2`, JavaScript uses string concatenation instead of numeric addition. For example, inputting 2 and 3 gives `"23"` instead of `5`. This was confirmed using the debugger — the Watch panel showed `typeof result: "string"` and the Scope panel showed `result: "23"`.

## How to fix it?
Wrap both values in `Number()` to explicitly convert them to numbers before adding:

Change line 9 from:
`let result = num1 + num2;`

To:
`let result = Number(num1) + Number(num2);`

This forces numeric addition instead of string concatenation.
