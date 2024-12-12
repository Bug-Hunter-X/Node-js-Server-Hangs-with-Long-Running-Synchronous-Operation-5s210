# Node.js Server Hang - Long-Running Synchronous Operation

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in the request handler blocks the event loop, causing the server to hang and become unresponsive.  The `server.js` file shows the problematic code, while `server-fixed.js` provides a solution using asynchronous operations.

## Problem

The original `server.js` uses a `while` loop to simulate a task that takes 5 seconds. This blocks the event loop, meaning no other requests can be processed until this loop completes.  This leads to a unresponsive server.

## Solution

The `server-fixed.js` demonstrates the correct approach using asynchronous operations to prevent blocking the event loop.  It uses `setTimeout` to simulate the long-running task, allowing other requests to be processed concurrently.