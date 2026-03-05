# Short Response Questions

Answer each question below in your own words. Aim for 3–5 sentences per answer. Be specific — use the exact terms and concepts from the lesson.

Your responses will each be evaluated out of 6 points. You can earn 3 points for writing quality and 3 points for the accuracy and precision of the technical content per question.

---

## Question 1: Express vs `node:http`

Express is described as a framework that "wraps" `node:http`. What does that mean? Compare how you would handle a `GET /api/users` request in `node:http` versus in Express. What does Express do for you automatically that you had to write manually with `node:http`?

**Your answer here**:

**Express** handles everything you had to do **manually** with `node:http`, reducing the **repetition**. If both were to make a response to a request, node:http would have to use `res.writeHead()` to set the **status** and specify the content type, and `res.end()` to send data. However, with Express, they would only use `res.send()` to send a **200 status**, which automatically sets the content type, and sends the given data.


---

## Question 2: Endpoints, Controllers, and Middleware

What are **controllers** and **middleware** in Express? What are each responsible for and how do they work together to handle incoming requests?

**Your answer here**:

**Middleware** is a function that is responsible for **receiving and processing** object requests, passing **control** to the next middleware in the chain. **Controllers** are a callback function responsible for parsing a request and sending a response when a request for the given **endpoint** is received. Middleware works as a controller that can be invoked for all incoming requests before the final controller sends a response.

---

## Question 3: Query Strings and Route Parameters

How are **query strings** and **route parameters** similar? How are they different? In your answer, provide an example of when you would use each.

**Your answer here**:

**query strings** and **route parameters** are similar because they both take data for the **request object**, but they differ in what data they take from. Query string takes from `req.query`, while route parameters take from `req.parms`. 

---

## Question 4: Same-Origin Requests

For API fetch calls from a client-side application, explain the difference between fetching from endpoints with relative paths like `/api/quotes` and fetching from endpoints with a full URL like `https://dog.ceo/api/breeds/image/random`. Why do we not send a fetch using a url like `http://localhost:8080/api/quotes`?

**Your answer here**:

When fetching from a **relative paths** it sends the request to the same host that served the page, while using a **full URL** will allow the browser to know exactly which **domain** and **protocol** to contact. But we do not send a fetch using a URL like `http://localhost:8080/api/quotes` because the relative paths will try to **fetch the request** in the wrong place, causing an error.