# Part 1

## Q1
Line 9 prints:

values added: 20

This is because `add` is true, so the code inside the if block runs and `result` is assigned the value `num1 + num2 = 10 + 10 = 20`.

---

## Q2
Line 13 prints:

final result: 20

There is no error because `var` is function-scoped, not block-scoped. Even though `result` is declared inside the if block, it is still accessible outside of the block within the function.

---

## Q3
You should not use `var` because it is function-scoped instead of block-scoped, which can lead to unexpected behavior and bugs. Variables declared with `var` can be accessed outside the block where they are defined, increasing the risk of accidental overwrites or conflicts. It is safer to use `let` or `const`, which are block-scoped.

---

## Q4
Line 9 prints:

values added: 20

This is because `add` is true, so the code inside the if block runs and `result` is assigned the value `num1 + num2 = 10 + 10 = 20`.

---

## Q5
Line 13 results in an error.

This is because `let` is block-scoped, meaning the variable `result` is only accessible inside the `if` block where it is defined. When line 13 tries to access `result` outside of that block, it causes a `ReferenceError` since `result` is not defined in that scope.

---

## Q6
Line 9 results in an error.

This is because `const` variables cannot be reassigned after they are declared. In the code, `result` is initialized as 0, but then the line `result = num1 + num2;` attempts to reassign it, which causes a `TypeError`.

---

## Q7
Line 13 is not executed because the code already throws an error before reaching it.

Additionally, even if the reassignment error did not occur, `result` would still not be accessible at line 13 because `const` is block-scoped (like `let`). Therefore, accessing it outside the `if` block would cause a `ReferenceError`.

---

