# Part 2

## Q1
Line 12 prints:

3

This is because `i` is declared with `var` inside the `for` loop. Since `var` is function-scoped, `i` is still accessible after the loop finishes. The loop stops when `i` becomes 3, so `console.log(i)` prints 3.

---

## Q2
Line 13 prints:

150

This is because `discountedPrice` is declared with `var`, which is function-scoped. Even though it is defined inside the `for` loop, it is still accessible outside the loop. After the loop finishes, `discountedPrice` holds the value from the last iteration, which is:

300 * (1 - 0.5) = 150

So `console.log(discountedPrice)` prints 150.

---

## Q3
Line 14 prints:

150

This is because `finalPrice` is declared with `var`, which is function-scoped. Even though it is updated inside the `for` loop, it remains accessible outside the loop. After the loop finishes, `finalPrice` holds the value from the last iteration, which is:

300 * (1 - 0.5) = 150

After rounding, the value remains 150, so `console.log(finalPrice)` prints 150.

---

## Q4
The function results in an error and does not return a value.

This is because `i` is declared with `let` inside the `for` loop, which makes it block-scoped. Therefore, `i` is not accessible outside the loop. When `console.log(i)` is executed, it causes a `ReferenceError` because `i` is not defined in that scope.

Since the error occurs before the `return` statement, the function does not successfully return the `discounted` array.

---

## Q5
Line 12 results in an error.

This is because `i` is declared with `let` inside the `for` loop, making it block-scoped. As a result, `i` is only accessible within the loop itself. When `console.log(i)` is executed outside the loop, it causes a `ReferenceError` because `i` is not defined in that scope.

---

## Q6
Line 13 results in an error.

This is because `discountedPrice` is declared with `let` inside the `for` loop, making it block-scoped. Therefore, it is only accessible within the loop. When `console.log(discountedPrice)` is executed outside the loop, it causes a `ReferenceError` because `discountedPrice` is not defined in that scope.

---

## Q7
Line 14 prints:

150

This is because `finalPrice` is declared with `let` outside the `for` loop, so it is accessible both inside and after the loop. During each iteration, `finalPrice` is updated, and after the loop finishes, it holds the value from the last iteration:

300 * (1 - 0.5) = 150

After rounding, the value remains 150, so `console.log(finalPrice)` prints 150.

---

## Q8
The function returns:

[50, 100, 150]

This is because the function iterates through each value in the `prices` array and applies the discount:

100 * (1 - 0.5) = 50  
200 * (1 - 0.5) = 100  
300 * (1 - 0.5) = 150  

Each result is rounded (though no change here) and pushed into the `discounted` array. After the loop finishes, the array `[50, 100, 150]` is returned.

There is no error because all variables are correctly scoped using `let`, and no out-of-scope variables are accessed.

---

## Q9
Line 11 results in an error.

This is because `i` is declared with `let` inside the `for` loop, making it block-scoped. Therefore, `i` is only accessible within the loop. When `console.log(i)` is executed outside the loop, it causes a `ReferenceError` because `i` is not defined in that scope.

---

## Q10
Line 12 prints:

3

This is because `length` is declared with `const` outside the loop, so it is accessible throughout the function. It stores the value of `prices.length`, which is 3. Since `length` is not modified, there is no error, and `console.log(length)` prints 3.

---

## Q11
The function returns:

[50, 100, 150]

This is because the function loops through each value in the `prices` array and applies the discount:

100 * (1 - 0.5) = 50  
200 * (1 - 0.5) = 100  
300 * (1 - 0.5) = 150  

Each discounted value is pushed into the `discounted` array. Since all variables are correctly scoped using `let` and `const`, no errors occur. The function successfully returns the array `[50, 100, 150]`.

---

## Q12

### A
student.name

### B
student["Grad Year"]

### C
student.greeting()

### D
student["Favorite Teacher"].name

### E
student.courseLoad[0]

---

## Q13

### A
'3' + 2 → '32'  
String concatenation occurs because one operand is a string.

### B
'3' - 2 → 1  
The string '3' is converted to number 3 for subtraction.

### C
3 + null → 3  
null is converted to 0.

### D
'3' + null → '3null'  
null is converted to string "null" and concatenated.

### E
true + 3 → 4  
true is converted to 1.

### F
false + null → 0  
false → 0 and null → 0.

### G
'3' + undefined → '3undefined'  
undefined is converted to string "undefined".

### H
'3' - undefined → NaN  
undefined cannot be converted to a valid number.

---

## Q14

### A
'2' > 1 → true  
'2' is converted to number 2.

### B
'2' < '12' → false  
String comparison is lexicographical: '2' > '1'.

### C
2 == '2' → true  
== performs type coercion.

### D
2 === '2' → false  
=== checks both value and type.

### E
true == 2 → false  
true → 1, so 1 != 2.

### F
true === Boolean(2) → true  
Boolean(2) is true, and both are boolean type.

---

## Q15

The `==` operator compares values with type coercion, meaning it converts operands to the same type before comparing.

The `===` operator compares both value and type without type conversion. It is stricter and generally safer to use.

---

## Q17
The function returns:

[2, 4, 6]

This is because the `modifyArray` function iterates through each element in the input array `[1, 2, 3]` and applies the `callback` function `doSomething` to each element.

The `doSomething` function multiplies each number by 2:

1 → 2  
2 → 4  
3 → 6  

Each result is pushed into a new array `newArr`, which is then returned. Therefore, the final result is `[2, 4, 6]`.

---

## Q19
The output is:

1  
4  
3  
2  

This is because JavaScript executes synchronous code first, followed by asynchronous callbacks.

- `console.log(1)` runs immediately.
- `setTimeout(..., 1000)` schedules `2` to run after 1 second.
- `setTimeout(..., 0)` schedules `3` to run after the current call stack is cleared.
- `console.log(4)` runs immediately.

After all synchronous code finishes, the event loop processes the callbacks:
- The `0ms` timeout (`3`) runs next.
- Finally, after 1 second, `2` is printed.
