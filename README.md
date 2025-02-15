# Stale Closure in useEffect with setInterval

This example demonstrates a common error in React when using the `useEffect` hook with `setInterval`.  The problem arises from the closure created within the `useEffect` callback. The `prevCount` variable within `setCount` does not always reflect the most up-to-date value of `count`, leading to unexpected and inconsistent behavior in the counter update.

The `bug.js` file contains the buggy code, while `bugSolution.js` provides the corrected version.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install the necessary dependencies.
3. Run `npm start` to start the development server.
4. Observe the counter's erratic behavior.

## Solution

The solution involves ensuring that the `setCount` function always accesses the latest state value.  This is often solved by refactoring the `setInterval` logic to use a ref or by using the `useRef` hook.