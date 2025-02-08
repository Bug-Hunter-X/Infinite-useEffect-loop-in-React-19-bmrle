# React 19 useEffect Infinite Loop Bug
This repository demonstrates a common mistake in React's `useEffect` hook that can lead to an infinite render loop, particularly noticeable in React 19.  The issue arises from omitting necessary dependencies in the `useEffect` hook's dependency array.

## Bug Description
The `bug.js` file contains a component with a `useEffect` hook that logs a message after every render.  However, because the `count` variable is not included in the dependency array, the effect runs continuously, causing the infinite loop.

## Solution
The `bugSolution.js` file demonstrates the correct way to fix the issue by including `count` in the dependency array. This ensures that the effect only runs when the `count` variable changes.

## How to Reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the console output in the browser.  The `bug.js` component should show an endless log of 'Effect ran!', whereas `bugSolution.js` will show it only once after the initial render and then whenever count changes. 

## Lesson Learned
Always carefully consider the dependencies you add to the `useEffect` hook's dependency array.  Missing dependencies can easily lead to unexpected behavior and performance issues.