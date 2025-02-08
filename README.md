# React setInterval Memory Leak
This example demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook.  The problem arises from the lack of a cleanup function to stop the interval when the component unmounts. This results in a memory leak.

## Bug Description
The `MyComponent` uses `setInterval` to update a counter every second. However, it fails to clear the interval when the component unmounts, leading to a memory leak.  The `setInterval` continues to run, consuming resources even after the component is no longer needed.

## Solution
The solution involves returning a cleanup function from the `useEffect` hook. This function will clear the interval when the component unmounts, preventing the memory leak.
