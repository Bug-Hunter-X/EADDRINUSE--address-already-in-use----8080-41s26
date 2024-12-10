# Node.js Port Binding Error: EADDRINUSE

This repository demonstrates a common Node.js error: `EADDRINUSE: address already in use :::8080`.  This occurs when your Node.js application tries to bind to a port that's already in use by another process (like another server, or even a process left over from a previous run).

The `bug.js` file shows the error-causing code. The `bugSolution.js` offers solutions to resolve this error.

## Solutions:

* **Check for existing processes:** Use tools like `netstat` (Linux/macOS) or `netstat -a -b` (Windows) to identify processes using port 8080.
* **Kill the process:** Once identified, terminate the process using the appropriate command (e.g., `kill <PID>` on Linux/macOS).
* **Use a different port:** Modify the server's `listen()` method to use an available port.
* **Implement error handling:** Handle the `EADDRINUSE` error gracefully within your Node.js application, perhaps by retrying after a delay or logging an appropriate message.
* **Check for zombie processes:** Ensure that you do not have any zombie processes that may be holding the port open.