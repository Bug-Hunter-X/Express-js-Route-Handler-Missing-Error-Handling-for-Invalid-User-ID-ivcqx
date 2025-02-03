# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input parameters.  Specifically, the `/users/:id` route does not handle the case where `:id` is not a valid integer.

## Bug

The `bug.js` file contains the erroneous code.  The route attempts to parse `req.params.id` as an integer using `parseInt()`. However, if `req.params.id` is not a number (e.g., a string, or undefined), `parseInt()` will return `NaN`, leading to issues in the `users.find()` function.

## Solution

The `bugSolution.js` file shows the corrected code.  It includes error handling to explicitly check if `req.params.id` can be parsed as an integer. If it's not a number, a 400 Bad Request error is returned.