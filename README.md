# React setInterval Memory Leak

This repository demonstrates a common error in React applications: memory leaks caused by using `setInterval` within the `useEffect` hook without proper cleanup.

## The Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it fails to include a cleanup function to clear the interval when the component unmounts. This leads to a memory leak as the interval continues to run even after the component is no longer displayed.

## The Solution
The `bugSolution.js` file provides the corrected component, where a cleanup function is added to the `useEffect` hook.  This function uses `clearInterval` to stop the interval when the component is unmounted, preventing the memory leak.

## How to reproduce
Clone this repo and run `npm install` to install the required dependencies. Then, run `npm start` to start the development server. Observe that the `bug.js` example does not correctly clean up on unmount which might cause problems such as slow performance and eventually crashing the page. In contrast, `bugSolution.js` shows correct usage of cleanup.