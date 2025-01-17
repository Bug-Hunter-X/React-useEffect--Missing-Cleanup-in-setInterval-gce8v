# React useEffect Hook: Missing Cleanup Function

This example demonstrates a common error in React's `useEffect` hook: forgetting to include a cleanup function when using `setInterval` or similar functions that create timers or subscriptions.  Without a cleanup function, these timers persist even after the component unmounts, leading to memory leaks and unexpected behavior.

## Bug

The `bug.js` file contains a component that uses `setInterval` to update a counter every second. However, it lacks the necessary cleanup function within the `useEffect` hook to clear the interval when the component unmounts.

## Solution

The `bugSolution.js` file corrects this by returning a cleanup function from `useEffect`. This function uses `clearInterval` to stop the interval when the component is no longer needed. This prevents memory leaks and ensures proper cleanup.