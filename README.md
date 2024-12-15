# Express.js - Empty req.body on POST Request
This repository demonstrates a common issue in Express.js applications where the req.body is empty despite sending JSON data in a POST request.  The problem is resolved by ensuring the correct middleware is used to parse the JSON payload.
## Bug
The `bug.js` file contains an Express.js application that attempts to handle POST requests with JSON data. However, due to a missing middleware, `req.body` remains empty.
## Solution
The `bugSolution.js` file provides the corrected application with the `express.json()` middleware included.  This middleware parses the incoming JSON requests and populates `req.body`.
## How to Reproduce
1. Clone the repository.
2. Run `npm install` to install Express.js.
3. Run `node bug.js`.
4. Send a POST request to `http://localhost:3000/data` with a JSON payload (e.g., using Postman or curl).
   You'll observe that the server logs an empty `req.body`.
5. Run `node bugSolution.js` and repeat step 4. This time `req.body` will contain the JSON data.
## Conclusion
This example highlights the importance of using the `express.json()` middleware when handling JSON data in Express.js applications.  Failure to include this middleware leads to unexpected behavior and errors.