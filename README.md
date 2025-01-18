# React Native: Asynchronous State Access

This repository demonstrates a common error in React Native: attempting to access state variables before they've been initialized.  The issue often arises in asynchronous operations or within `useEffect` hooks before the first render.

## Problem

The `bug.js` file shows a component that uses `setInterval` to update a state variable.  However, `console.log(count)` inside the `useEffect` might log `undefined` initially because the state hasn't finished initializing.

## Solution

The `bugSolution.js` file presents a corrected version that uses the previous state value (`prevCount`) with `useState`'s functional update to address the issue.  This guarantees that the state is always accessed safely.