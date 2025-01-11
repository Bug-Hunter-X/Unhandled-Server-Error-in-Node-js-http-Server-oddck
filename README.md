# Node.js Unhandled Server Error

This repository demonstrates a common, yet subtle, error in Node.js HTTP server implementations: the lack of error handling during server initialization.  The `bug.js` file showcases the problematic code, while `bugSolution.js` provides a corrected version that gracefully handles potential errors.

## Problem

The original code directly uses `server.listen()` without error handling. If the port is already in use or another issue occurs during startup, the server crashes without any informative error message. 

## Solution

The solution involves using the `error` event listener provided by the `http.Server` object. This listener captures any errors during server startup and allows for appropriate handling (e.g., logging, retrying, or exiting gracefully).