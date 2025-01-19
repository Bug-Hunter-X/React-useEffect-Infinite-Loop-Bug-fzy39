# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: creating an infinite loop by directly modifying the state variable within the effect's callback. The `bug.js` file contains the buggy code, while `bugSolution.js` provides the corrected version.

## Problem

The `useEffect` hook in `bug.js` attempts to increment the `count` state variable within the effect itself.  Because this happens within the same render cycle that triggers the `useEffect`, it causes an infinite loop of re-renders.

## Solution

The solution in `bugSolution.js` demonstrates the correct way to update state within an effect.  Instead of directly assigning a new value, it uses the state's setter function (`setCount`) to update it asynchronously.  This ensures that React correctly schedules the re-render, avoiding the infinite loop.
