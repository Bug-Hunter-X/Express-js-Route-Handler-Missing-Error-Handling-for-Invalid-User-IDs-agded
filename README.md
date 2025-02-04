# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling when dealing with user input.  Specifically, the code attempts to parse a user ID from a route parameter but does not handle the case where the ID is not a valid number or is missing.

## Bug

The `bug.js` file contains the buggy code.  It fetches a user based on the ID from the URL. If the ID is invalid or the user is not found, it will crash or respond unexpectedly.

## Solution

The `bugSolution.js` file provides a corrected version that adds error handling to gracefully handle invalid user IDs and missing users, returning appropriate HTTP status codes (400 for bad requests and 404 for not found).

## How to reproduce

1. Clone this repository.
2. Run `npm install express`.
3. Run `node bug.js` and navigate to `/users/abc` or `/users/12345` to test.  Observe the error (or lack thereof) in the console and the server response.
4. Repeat with `node bugSolution.js` to see the improved behavior.