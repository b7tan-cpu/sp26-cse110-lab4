# DevTools Part 2

## What was the bug?

The bug was that `num1` and `num2` were read from the input elements using `.value`, which returns strings. Because of this, the `+` operator performed string concatenation instead of numeric addition.

For example, entering 1 and 2 produced `12` instead of `3`.

## How would you fix it?

I would fix it by converting the input values to numbers before passing them into `calculateSum()`:

```js
let num1 = Number(document.getElementById("num1").value);
let num2 = Number(document.getElementById("num2").value);