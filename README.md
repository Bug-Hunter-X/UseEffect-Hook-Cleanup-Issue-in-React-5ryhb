# React useEffect Cleanup Issue

This repository demonstrates a common issue related to the `useEffect` hook in React: improper cleanup in an effect with an empty dependency array.  The example shows a component that logs 'Mounted!' once upon mounting, but may have additional cleanup logic that isn't handled correctly, leading to potential memory leaks or unexpected behavior when the component unmounts.

## Problem

The provided `bug.js` file contains a component that utilizes `useEffect` with an empty dependency array ([]). While this correctly ensures the effect runs only once upon mounting, it demonstrates the potential for failure to handle asynchronous operations or resource cleanup. If the effect were to initiate a long-running task or hold onto resources, those would not be cleaned up when the component is unmounted.  

## Solution

The `bugSolution.js` file offers a solution illustrating proper cleanup using the return function within the `useEffect` hook. The cleanup logic (in this example, logging 'Unmounted!') ensures that resources are released when the component is no longer needed. The solution focuses on addressing the potential for subtle memory leaks or unintended consequences caused by ignoring cleanup in an empty dependency array effect.
