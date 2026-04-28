# Part 2

## Question 1
Line 12 prints: `3`
`var i` is function-scoped. After the loop finishes, `i` equals `prices.length` which is 3, and it is still accessible outside the loop.

## Question 2
Line 13 prints: `150`
`var discountedPrice` is function-scoped. It retains the value from the last loop iteration: `300 * (1 - 0.5) = 150`.

## Question 3
Line 14 prints: `150`
`var finalPrice` is function-scoped and retains its last assigned value of `150` after the loop ends.

## Question 4
The function returns: `[50, 100, 150]`
Each price in `[100, 200, 300]` is multiplied by `(1 - 0.5)` to get the discounted price, rounded, and pushed to the `discounted` array.

## Question 5
Line 12 throws a ReferenceError.
`let i` is block-scoped to the `for` loop. It does not exist outside the loop, so accessing it at line 12 throws a ReferenceError.

## Question 6
Line 13 throws a ReferenceError.
`let discountedPrice` is block-scoped to the loop body `{}`. It is not accessible outside that block.

## Question 7
Line 14 prints: `150`
`let finalPrice` is declared outside the loop at function scope, so it is accessible after the loop ends and holds the last assigned value of `150`.

## Question 8
The function returns: `[50, 100, 150]`
Same result as Question 4. `let finalPrice` is updated each iteration and pushed correctly.

## Question 9
Line 11 throws a ReferenceError.
`let i` is block-scoped to the `for` loop and is not accessible outside it.

## Question 10
Line 12 prints: `3`
`const length = prices.length` is declared at function scope, so it is accessible after the loop. Its value is `3`.

## Question 11
The function returns: `[50, 100, 150]`
`const discounted` is declared at function scope and is never reassigned (only `.push()` is called on it), so no error occurs. The function correctly returns the discounted prices.

---

## Question 12 - Object Notation
Given the student object, the notation for each is:

A. `student.name`
B. `student['Grad Year']`
C. `student.greeting()`
D. `student['Favorite Teacher'].name`
E. `student.courseLoad[0]`

---

## Question 13 - Arithmetic

A. `'3' + 2` → `'32'` — The `+` operator with a string triggers string concatenation, so `2` is coerced to `"2"`.
B. `'3' - 2` → `1` — The `-` operator has no string behavior, so `'3'` is coerced to the number `3`. `3 - 2 = 1`.
C. `3 + null` → `3` — `null` coerces to `0` in numeric context. `3 + 0 = 3`.
D. `'3' + null` → `'3null'` — `+` with a string triggers concatenation. `null` coerces to the string `"null"`.
E. `true + 3` → `4` — `true` coerces to `1` in numeric context. `1 + 3 = 4`.
F. `false + null` → `0` — `false` coerces to `0`, `null` coerces to `0`. `0 + 0 = 0`.
G. `'3' + undefined` → `'3undefined'` — `+` with a string triggers concatenation. `undefined` coerces to `"undefined"`.
H. `'3' - undefined` → `NaN` — `-` coerces both sides to numbers. `undefined` becomes `NaN`, and any arithmetic with `NaN` returns `NaN`.

---

## Question 14 - Comparison

A. `'2' > 1` → `true` — `'2'` is coerced to the number `2`. `2 > 1` is `true`.
B. `'2' < '12'` → `false` — Both are strings, so comparison is alphabetical. `'2'` comes after `'1'`, so `'2' < '12'` is `false`.
C. `2 == '2'` → `true` — Loose equality coerces `'2'` to `2`. `2 == 2` is `true`.
D. `2 === '2'` → `false` — Strict equality checks type and value. `number !== string`, so `false`.
E. `true == 2` → `false` — `true` coerces to `1`. `1 == 2` is `false`.
F. `true === Boolean(2)` → `true` — `Boolean(2)` evaluates to `true`. `true === true` is `true`.

---

## Question 15
The `==` operator (loose equality) performs type coercion before comparing, meaning it converts operands to the same type before checking equality. The `===` operator (strict equality) checks both value and type without any coercion — both sides must be the same type and value to return `true`. In general, `===` should be preferred to avoid unexpected results from implicit type conversion.

---

## Question 17 - Callback
When called with `modifyArray([1,2,3], doSomething)`, the result is `[2, 4, 6]`.

The `modifyArray` function iterates over the input array `[1, 2, 3]`. For each element, it calls `doSomething(element)`, which returns `num * 2`. The result of each callback call is pushed to `newArr`. So `1` becomes `2`, `2` becomes `4`, and `3` becomes `6`, giving a final result of `[2, 4, 6]`.

---

## Question 19 - setTimeout output
The output is:
1
4
3
2
`console.log(1)` runs first synchronously. Then both `setTimeout` calls are queued asynchronously — even the 0ms one does not run immediately. `console.log(4)` runs next synchronously. Then the 0ms timeout fires, printing `3`. Finally, after 1000ms, the other timeout fires, printing `2`.
