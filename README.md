# JavaScript Loose Comparison Bug

This repository demonstrates a common, yet subtle bug in JavaScript related to loose comparison in conditional statements. The code appears to function correctly at first glance but produces unexpected results due to JavaScript's handling of falsy values in loose comparison (`==` or `!=`).

## Bug Description

The provided JavaScript function `foo` intends to return 0 if the input `x` is null, -1 if `x` is negative, and 1 otherwise.  However, because of JavaScript's loose comparison, the condition `x < 0` will incorrectly evaluate to `true` when `x` is 0. This is because 0 is considered a falsy value in JavaScript, leading to the `else` block being executed, unexpectedly returning 1 when the input is 0.

## Solution

To fix this, always use strict equality (`===` and `!==`) when comparing values in JavaScript, to prevent unintended type coercion. The solution uses `===` and `!==` to ensure the conditional statement correctly evaluates the input type and numerical value.