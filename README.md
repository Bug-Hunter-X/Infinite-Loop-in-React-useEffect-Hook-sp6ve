# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The provided `MyComponent` uses `useEffect` without a dependency array, leading to an infinite render loop.

## Problem

The `useEffect` hook is designed to perform side effects after a component renders.  However, if no dependency array is provided (or an incorrect one), the effect will run after every render, creating a loop. In this case, `console.log` isn't computationally expensive, but in real-world scenarios, this can cause severe performance problems.

## Solution

The solution is to provide a dependency array to the `useEffect` hook.  The array should list all values from the component's scope that the effect depends on. If it depends on nothing, pass an empty array `[]`.