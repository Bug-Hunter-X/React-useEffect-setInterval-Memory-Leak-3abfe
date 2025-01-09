# React useEffect setInterval Memory Leak
This repository demonstrates a common mistake when using the `useEffect` hook with `setInterval` in React: forgetting to include a cleanup function to prevent memory leaks.

## Bug Description
The `bug.js` file contains a component that uses `useEffect` to set up an interval.  However, it omits the return function required to clear the interval when the component unmounts or when dependencies change, leading to a memory leak.

## Solution
The `bugSolution.js` file corrects the issue by adding a return function to the `useEffect` hook. This return function calls `clearInterval` to stop the interval when it's no longer needed, preventing the memory leak.

## How to reproduce
1. Clone this repository
2. Run `npm install`
3. Run `npm start`
Observe the memory usage in your browser's developer tools for both `bug.js` and `bugSolution.js` versions to see the difference.