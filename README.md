# React Native FlatList/SectionList: Silent Errors from Missing `renderItem` Properties

This repository demonstrates a common yet subtle bug in React Native's FlatList and SectionList components. The issue arises when the `renderItem` function attempts to access properties of the `item` prop that might be missing in some data elements.  This often results in silent failures without clear error messages, making debugging challenging.

## The Bug
The bug is demonstrated in `bug.js`.  The `renderItem` function accesses the `item.description` property. However, the data array might contain items *lacking* a `description` property. Accessing a non-existent property might cause an unexpected behavior or a crash without a stack trace, making it hard to pinpoint the problem.

## The Solution
The solution in `bugSolution.js` uses optional chaining (`?.`) to safely access the `description` property. Optional chaining prevents errors when the property is undefined or null, providing a more robust solution.