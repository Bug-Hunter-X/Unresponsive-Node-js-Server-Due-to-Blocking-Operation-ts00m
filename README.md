# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js applications: an unresponsive server caused by a long-running synchronous operation that blocks the event loop. The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

The problem lies in the request handler of the HTTP server. The `while` loop simulates a long-running task that keeps the CPU busy for 5 seconds. During this time, the event loop is blocked, and the server cannot process any other incoming requests. This leads to unresponsiveness and poor performance.

## Solution

The solution involves refactoring the code to use asynchronous operations.  This allows the event loop to continue processing other requests while the long-running task is being executed in the background.