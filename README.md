# Node.js Server Unresponsiveness Due to Long-Running Requests

This repository demonstrates a common issue in Node.js applications: server unresponsiveness caused by long-running operations that block the event loop.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

The original code uses `setTimeout` to simulate a long-running task within the request handler.  Because this is a synchronous operation, the event loop is blocked for the entire 5 seconds, making the server unresponsive to other requests during that time.

## Solution

The solution utilizes asynchronous operations to prevent blocking the event loop.  Instead of using `setTimeout` directly, it now uses asynchronous functions and callbacks or promises to offload the work to separate threads or events, so the event loop remains free to process other requests.