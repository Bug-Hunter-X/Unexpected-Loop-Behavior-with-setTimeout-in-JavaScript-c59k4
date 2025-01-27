# Unexpected Loop Behavior with setTimeout in JavaScript

This repository demonstrates a common JavaScript closure issue that arises when using `setTimeout` within a loop.  The expected behavior is to print the numbers 0 through 9 sequentially after a one-second delay. However, due to how closures work in JavaScript, this code produces unexpected results.

## Bug Description

The problem stems from the fact that the `setTimeout` callback doesn't immediately execute. By the time the callbacks finally execute, the loop has already completed, and the variable `i` will have its final value of 10.  Therefore, all the callbacks will log the same value.

## Solution

The solution involves using an immediately invoked function expression (IIFE) or `let` in a different manner to create a new scope for each iteration of the loop. This ensures that a unique value of `i` is captured for each callback.  See the `bugSolution.js` file for an effective fix.