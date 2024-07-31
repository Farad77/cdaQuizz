# Correction du Questionnaire sur Node.js

## Questions à choix unique (en français)

1. Quel module Node.js est utilisé pour créer un serveur HTTP ?
   
   Réponse correcte : a) http
   
   Explication : Le module 'http' est un module core de Node.js qui permet de créer des serveurs HTTP et de faire des requêtes HTTP. Il fournit des fonctionnalités pour gérer les requêtes et les réponses HTTP.

2. Quelle est la commande pour installer un package npm ?
   
   Réponse correcte : c) npm install package-name
   
   Explication : La commande 'npm install' est utilisée pour installer des packages depuis le registre npm. Par exemple, 'npm install express' installerait le framework Express.js.

## Questions ouvertes (en anglais)

1. Explain the concept of the event loop in Node.js and why it's important.

   Réponse modèle : 
   The event loop is a fundamental concept in Node.js that allows it to perform non-blocking I/O operations despite JavaScript being single-threaded. It works by offloading operations to the system kernel whenever possible and executing callbacks when these operations complete.

   The event loop continuously checks if there are any tasks in the queue that need to be executed. If there are, it takes the first task and executes its callback. This process repeats until the queue is empty.

   The importance of the event loop lies in its ability to handle many operations concurrently without the need for multi-threading. This makes Node.js highly scalable and efficient, especially for I/O-bound applications like web servers. It allows Node.js to handle thousands of concurrent connections with a single server without introducing the complexity of multi-threaded programming.

2. What is middleware in Express.js and how is it used?

   Réponse modèle:
   Middleware in Express.js refers to functions that have access to the request object (req), the response object (res), and the next middleware function in the application's request-response cycle, commonly denoted by a variable named 'next'.

   Middleware functions can:
   1. Execute any code.
   2. Make changes to the request and response objects.
   3. End the request-response cycle.
   4. Call the next middleware in the stack.

   Middleware is used for various purposes such as:
   1. Parsing request bodies
   2. Handling CORS
   3. Logging
   4. Error handling
   5. Authentication

   To use middleware in Express.js, you can use the app.use() method. For example:

   ```javascript
   app.use((req, res, next) => {
     console.log('Time:', Date.now());
     next();
   });
   ```

   This middleware will log the timestamp for every request. The 'next()' function is called to pass control to the next middleware function.

   Middleware can be application-level, router-level, error-handling, built-in, or third-party. It's a powerful feature that allows for modular and flexible application structure in Express.js.

