# Express.js Route Handler: Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers:  the lack of proper error handling for invalid input.  The `bug.js` file contains code that is vulnerable to crashes when a non-numeric ID is provided to the `/users/:id` route.  The `bugSolution.js` file shows how to improve the code with robust error handling.

## Bug Description

The buggy code fails to handle cases where `req.params.id` is not a valid integer.  Attempting to parse a non-numeric string with `parseInt()` can lead to unexpected behavior, potentially resulting in errors within the `users.find()` method or elsewhere.

## Solution

The solution involves adding input validation to ensure that `req.params.id` is a valid integer before attempting to use it.  This helps prevent crashes and provides more informative error responses to the client.