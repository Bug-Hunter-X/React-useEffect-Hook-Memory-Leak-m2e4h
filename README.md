# React useEffect Hook Memory Leak

This example demonstrates a common mistake when using the `useEffect` hook in React: forgetting to return a cleanup function. This can lead to memory leaks if the component unmounts before the effect completes.

## Bug

The `useEffect` hook in `bug.js` does not return a cleanup function. This means that even if the component unmounts, the effect will continue to run, potentially causing memory leaks.

## Solution

The solution in `bugSolution.js` adds a cleanup function to the `useEffect` hook. This ensures that the effect is properly cleaned up when the component unmounts.  The cleanup function prevents potentially problematic actions, such as event listeners or timers that were registered within the effect, from continuing after the component is removed from the DOM.