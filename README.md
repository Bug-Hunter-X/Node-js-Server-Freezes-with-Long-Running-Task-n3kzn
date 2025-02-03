# Node.js Server Freeze
This repository demonstrates a common issue in Node.js where a long-running task in the request handler can freeze the server, making it unresponsive to new requests.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations to prevent the freeze.

## Problem
The original `server.js` uses a simple `for` loop to simulate a computationally intensive task.  This blocks the event loop, preventing the server from processing other requests until the loop completes.  This results in a frozen server. 

## Solution
The solution in `serverSolution.js` leverages asynchronous operations to prevent the blocking behavior.  The work is offloaded to allow the server to remain responsive. This improved code keeps the server running smoothly even under heavy load, handling multiple requests concurrently.