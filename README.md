## How to use this Repo

This repo has three branches:

* master
* final
* final-all-in-one

The `master` branch has a starter template for creating what is in the `final` branch.  The `final-all-in-one` is a single `app-all.js` file that functions completely alone, while the `final` branch is a refactored version of that.

## How to run the app

When you go to each branch, the `README.md` will show you how to start the app.

The `master` branch is incomplete and you can follow the written or video tutorials to complete:

* Written - https://zachgoll.github.io/blog/2019/choosing-authentication-strategy/
* Video - Coming soon

## Notes
1. Express.js, or simply Express, is a free, open-source, lightweight, and fast backend web application framework for Node.js
2. Features: 
   - js can be used to design single-page, multi-page, and hybrid web applications and APIs.
      - You can render static html files stored on your server, to render dynamic content using ejs. Can also add libraries to these files ( like react, angular, bootstrap, bootswatch, custom fonts etc )
   - It allows to set up middleware to respond to HTTP/RESTful Requests.
      - Middleware as the name tells is a function that you want to call in the middle of something.
      - eg: beforing sending a resource we would like to check if user is authenticated or is authorised. We can make a function that will be called first then only the next thing is done. Such a function is called a middleware 
   - It defines a routing table to perform different HTTP operations (method and URL).
   - It allows to dynamically rendering HTML Pages based on passing arguments to templates.
      - express handlebars can be used for the same
   - It provides high performance because of its ultra-fast I/O. It prepares a thin layer; therefore, the performance is adequate.
   - Its MVC-like structure makes it organize the web  application into MVC architecture.
   - It provides good database support. It supports RDBMS as well as NoSQL databases.
   - It is asynchronous and single-threaded.
    Its robust API makes routing easy.
<br>
<br>

3. Scaffolding in Express.js is a technique used for creating the skeleton structure of an application. It facilitates users to easily create their public directories, routes, views, etc., or a web application skeleton. Generally, users manually create their public directory, add middleware, create separate route files, etc. Using a scaffolding tool, they can set up all these things to directly get started with building their application.

   - There are two ways to install Scaffolding and use it in your application.
       - Express application generator
          - Summary: 
            <br>
            `npm install express-generator -g`  
            `express myApp `
            <br>
            The above command creates a project named "myApp" along with the folowwing files/folders : `bin, public, routes, views, app.js, package.json`
       - Yeoman

4. Arguments available to an express JS route handler function : req, res, next (optional)

5. Error handling in express.js
   - Create a middleware for error handling. 
   - add it to the express - app object at the end ( making it a global middleware )

6. Code to start serving static files in express.js
~~~
  app.use(express.static('public'))  
  app.use('/static', express.static(path.join(__dirname, 'public')))  
~~~      

7. Middleware is a function invoked by the Express routing layer before the final request handler.
Middleware functions are used to perform the following tasks:

   - It is used to execute any code.
   - It is also used to make changes to the request and the response objects.
   - It is responsible for ending the request-response cycle.
   - It can call the next middleware function in the stack.

8. Types of middleware
  - Application-level Middleware : Used to bind to the app object using app.use() method. It applies to all the routes.
  ~~~
    //This middleware will execute for each route.  
    app.use(function (req, res, next) {  
      console.log('Current Time:', Date.now())  
      next()  
    })  
  ~~~
  - Router-level Middleware : This is used to bind to a specific instance of express.Router(). 
  - Error-handling Middleware
  - Built-in Middleware : static, json, urlencoded
  - Third-party Middleware: 
      - Body-parser
      - Cookie-parser
      - Mongoose
      - Sequelize
      - Cors
      - Express-validator

9. HTTP protocols are stateless and therefore we use cookies to store infor related to auth like tokens. So that user does not have to authenticate ( by enterring credentials) on each page refresh/reload. 
  - Set cookie header can be used to add key value pairs to cookie object