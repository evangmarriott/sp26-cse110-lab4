# Part 1

## Question 1
Line 9 prints: `values added: 20`
`var result` is assigned `num1 + num2 = 10 + 10 = 20` and logged on line 9.

## Question 2
Line 13 prints: `final result: 20`
Because `var` is function-scoped, `result` is still accessible outside the `if` block and retains the value 20.

## Question 3
You should not use `var` because it is function-scoped rather than block-scoped. This means variables declared with `var` leak out of blocks like `if` statements and `for` loops, which can lead to naming conflicts, unexpected behavior, and bugs that are hard to track down.

## Question 4
Line 9 prints: `values added: 20`
`let result` is assigned `num1 + num2 = 20` and logged.

## Question 5
Line 13 throws a ReferenceError.
`let result` is block-scoped to the `if` block. Once outside that block, `result` no longer exists in scope.

## Question 6
Line 9 throws a TypeError.
`const result = 0` cannot be reassigned. Line 7 tries to reassign it with `result = num1 + num2`, which throws a TypeError before line 9 is ever reached.

## Question 7
Line 13 is never reached.
The TypeError from line 7 (attempting to reassign a `const`) prevents execution from continuing.
