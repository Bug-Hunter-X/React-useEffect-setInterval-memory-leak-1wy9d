# React useEffect setInterval memory leak
This example demonstrates a common mistake when using `setInterval` within a React `useEffect` hook: forgetting to return a cleanup function to clear the interval when the component unmounts. This can lead to memory leaks and unexpected behavior.

## Bug
The `bug.js` file contains a component that uses `setInterval` to update a counter every second. However, it fails to provide a cleanup function within the `useEffect` hook to clear the interval when the component unmounts. This results in the interval continuing to run even after the component is removed from the DOM, leading to a memory leak.

## Solution
The `bugSolution.js` file corrects this issue by returning a function from the `useEffect` hook. This function clears the interval using `clearInterval` when the component unmounts, preventing the memory leak.