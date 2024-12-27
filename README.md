# Unexpected null value for useRef.current in React Native

This repository demonstrates a common, yet subtle, bug in React Native involving the `useRef` hook.  The issue arises when the `current` property of a ref is accessed, and it unexpectedly returns `null`, even after the component has mounted.

## Problem
The problem is that accessing a ref immediately after rendering or within certain lifecycle methods might result in the ref's `current` property not yet being assigned the correct value.  This is due to the asynchronous nature of rendering in React.

## Solution
The solution involves ensuring that the ref is accessed only *after* the component has fully mounted and rendered. This can be achieved using the `useEffect` hook and checking that the ref is not null before accessing its `current` property.