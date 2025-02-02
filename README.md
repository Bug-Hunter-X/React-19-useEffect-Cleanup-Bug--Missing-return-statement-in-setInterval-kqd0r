# React 19 useEffect Cleanup Bug
This example demonstrates a common mistake in React 18 and 19's `useEffect` hook: forgetting to include a return statement for cleanup when using `setInterval` or `setTimeout`.  This can lead to memory leaks and unexpected behavior.

## Bug
The `bug.js` file shows an incorrect implementation of `useEffect` where a `setInterval` is used without a cleanup function. When the component unmounts, the interval continues to run, causing a memory leak.

## Solution
The `bugSolution.js` file demonstrates the correct implementation. The `useEffect` hook now includes a return statement which clears the interval using `clearInterval` when the component unmounts preventing the memory leak.  This ensures that resources are properly released.

## How to reproduce
1. Clone this repository
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe that the `bug.js` component will continue to increment even after unmounting (though this may depend on your React development setup).
5. The corrected `bugSolution.js` will behave correctly.