# Node.js Server Unresponsiveness under Load

This repository demonstrates a common issue in Node.js applications: unresponsiveness to new connections when a long-running request blocks the event loop.  The `server.js` file contains a simple HTTP server that simulates a long-running task.  When this task runs, the server becomes unresponsive to subsequent requests. This is a classic example of the Node.js event loop getting blocked.  The solution, provided in `serverSolution.js`, addresses this using asynchronous operations to prevent blocking.

## How to reproduce the bug:
1. Clone this repository.
2. Run `node server.js`
3. Open multiple browser tabs and try to access `http://localhost:3000`.  You'll observe that after one request that takes 5 seconds to process, subsequent requests will hang or time out.

## Solution:
The `serverSolution.js` demonstrates how to refactor this to use asynchronous patterns avoiding the blocking of the event loop.  This demonstrates how to make a Node.js application more responsive and handle concurrent requests efficiently.