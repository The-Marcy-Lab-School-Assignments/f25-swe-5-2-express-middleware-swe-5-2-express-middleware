# Short Response Questions

Answer each question below in your own words. Aim for 3–5 sentences per answer. Be specific — use the exact terms and concepts from the lesson.

Your responses will each be evaluated out of 6 points. You can earn 3 points for writing quality and 3 points for the accuracy and precision of the technical content per question.

---

## Question 1: Express vs `node:http`

Express is described as a framework that "wraps" `node:http`. What does that mean? Compare how you would handle a `GET /api/users` request in `node:http` versus in Express. What does Express do for you automatically that you had to write manually with `node:http`?

**Your answer here**:

---Express “wraps” node:http means it builds on top of Node’s built-in HTTP module and makes handling requests easier. In node:http, you have to manually check the request method and URL, parse data, and send responses. For example, to handle GET /api/users, you would check req.method === 'GET' and req.url === '/api/users' and then manually send JSON. In Express, you just write app.get('/api/users', (req, res) => { res.json(users) }). Express automatically parses URLs, handles headers, and lets you send JSON easily without writing all the low-level code

## Question 2: Endpoints, Controllers, and Middleware

What are **controllers** and **middleware** in Express? What are each responsible for and how do they work together to handle incoming requests?

**Your answer here**:

---Controllers are functions that handle the logic for a specific endpoint, like returning users or creating a post. Middleware are functions that run before controllers to process the request, like logging, parsing JSON, or checking authentication. They work together because middleware can prepare or validate data, and then the controller uses that data to respond to the client.

## Question 3: Query Strings and Route Parameters

How are **query strings** and **route parameters** similar? How are they different? In your answer, provide an example of when you would use each.

**Your answer here**:

---Query strings and route parameters both pass data in the URL. Route parameters are part of the URL path, like /users/:id, and are used for identifying specific resources. Query strings come after ?, like /users?id=5, and are used for filtering, sorting, or optional data. For example, use a route parameter to get a user by ID (/users/123) and a query string to filter users by age (/users?age=30).

## Question 4: Same-Origin Requests

For API fetch calls from a client-side application, explain the difference between fetching from endpoints with relative paths like `/api/quotes` and fetching from endpoints with a full URL like `https://dog.ceo/api/breeds/image/random`. Why do we not send a fetch using a url like `http://localhost:8080/api/quotes`?

**Your answer here**:
Fetching with a relative path like /api/quotes means the request goes to the same server and port as your client app. Using a full URL like https://dog.ceo/api/breeds/image/random fetches from a different server (cross-origin). We don’t use http://localhost:8080/api/quotes in the browser when the frontend is served from another port because it can cause CORS issues. Relative paths are safer for same-origin requests and work automatically with Express.