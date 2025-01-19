# Closure in Loop with setTimeout

This example demonstrates a common JavaScript error related to closures within loops when using `setTimeout` or other asynchronous functions.

## Problem

The `myFunction` attempts to print numbers 0 through 9 with a one-second delay between each number. However, due to how closures work in JavaScript, each `setTimeout` callback refers to the final value of `i` (which is 10) after the loop has completed.  Therefore, '10' is printed ten times instead of the expected sequence.

## Solution

The solution uses an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop. This ensures each callback has its own copy of the `i` variable at the time of execution.