# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)


- **[<code>GET</code> /api/v1/merchants](https://byob-pam.herokuapp.com/api/v1/merchants )**
- **[<code>GET</code> /api/v1/merchants/:merchant_id](https://byob-pam.herokuapp.com/api/v1/merchants/125427)**
- **[<code>GET</code> /api/v1/products](https://byob-pam.herokuapp.com/api/v1/products)**
- **[<code>GET</code> /api/v1/products/:id](https://github.com/500px/api-documentation/blob/master/endpoints/photo/GET_photos_id_comments.md)**
- **[<code>GET</code> /api/v1/merchantName](https://byob-pam.herokuapp.com/api/v1/merchantName?merchant_name=Sur%20La%20Table)**
- **[<code>PATCH</code> /api/v1/products/:id/edit](https://byob-pam.herokuapp.com/api/v1/products)**
- **[<code>PUT</code> /api/v1/products/:id/replace](https://byob-pam.herokuapp.com/api/v1/products)**
- **[<code>POST</code> /api/v1/merchants](https://byob-pam.herokuapp.com/api/v1/merchants)**
- **[<code>POST</code> /api/v1/products](https://byob-pam.herokuapp.com/api/v1/products)**
- **[<code>DELETE</code> /api/v1/merchants/:merchant_id](https://byob-pam.herokuapp.com/api/v1/merchants)**
- **[<code>DELETE</code> /api/v1/products/:id](https://byob-pam.herokuapp.com/api/v1/products)**

------

# Basics

#### Link to the Github Repository for the Project
[Build Your Own BE](https://github.com/thatPamIAm/build_your_own_be)

#### Link to the Deployed Application
[Deployed build on heroku](https://byob-pam.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/thatPamIAm/build_your_own_be/commits/development)

## Completion

#### Were you able to complete the base functionality?

* Seeded a database with at least 2 tables and 1 relationship?
Yes

* Had at least 10 endpoints that returned responses with appropriate status codes?
Yes

* Secured at least 4 endpoints with JWTs?
Yes

* Enforced a linter and wrote code that conformed to it?
Yes

* Wrote tests for both happy and sad paths for each endpoint?
Yes

* Setup automatic deployments with CircleCI to a production app on Heroku?
Yes

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Code I'm proud of](https://github.com/thatPamIAm/build_your_own_be/blob/development/server.js#L101-L112)

* Why were you proud of this piece of code?

I'm proud that I was able to get the custom endpoint working, especially after having to use custom endpoints to hit the API I wanted for my project.

#### Link to a specific block of your code on Github that you feel not great about
[Meh code](https://github.com/thatPamIAm/build_your_own_be/blob/development/server.js#L146-L160)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

I couldn't get my test for this endpoint to pass, which I believe has something to do with my using a unique column in my primary table as the foreign key in my secondary - as this is what the error continuously points to as being wrong.
## Testing
![](http://i.imgur.com/7vAZeG2.png)

## Linting

![](http://i.imgur.com/nLfjbhk.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

-----

## Instructor Evaluation Points (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Endpoints

* **60 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params.

* [This route](https://github.com/thatPamIAm/build_your_own_be/blob/development/test/routes.spec.js#L264) is a little unconventional in terms of being "RESTful". A more conventional route for this case would be to filter on the merchants for the merchant name: `/api/v1/merchants?name=SomeMerch`

### Data Persistence with SQL Database

* **40 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

* Ideally, the [foreign key](https://github.com/thatPamIAm/build_your_own_be/blob/development/db/migrations/20170517114658_renameForeignColumn.js) is the primary key from the merchants table, but I understand the schema based on the data you were using - otherwise, good implementation of a one-to-many relationship

### Testing & Linting

* **25 points** - Project has a running test suite that covers most happy and sad paths for each endpoint. Linter has some errors that need fixing.

* Depending on the [`afterEach` block](https://github.com/thatPamIAm/build_your_own_be/blob/development/test/routes.spec.js#L25-L30) to re-seed your database can bite you if a test fails because the `afterEach` will not run after a test failure, and you could be left with the database in a weird state for the test that follows the failure
* Can test for property values in [these tests](https://github.com/thatPamIAm/build_your_own_be/blob/development/test/routes.spec.js#L67) even when you don't know the order of items in the array
* When you're returning a [single resource](https://github.com/thatPamIAm/build_your_own_be/blob/development/test/routes.spec.js#L90), it's usually not nested in an array - you would just send over the object that was found in the database
* Good status code [here](https://github.com/thatPamIAm/build_your_own_be/blob/development/test/routes.spec.js#L253)
* There are a few tests like [this one](https://github.com/thatPamIAm/build_your_own_be/blob/development/test/routes.spec.js#L191) that are testing paths that are _close_ to the route, but a little off - they are basically testing your 404 scenario. You can do this once, but beyond that it's a little redundant

### JavaScript Style

* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* When you have a lot of routes in the server file, it's a good idea to break the routes out into other files know as `routers`. Take a look at the [Express documentation](https://expressjs.com/en/api.html#router) to see how they work.
* I appreciate [this](https://github.com/thatPamIAm/build_your_own_be/blob/development/server.js#L17)
* Not sure about [this catch](https://github.com/thatPamIAm/build_your_own_be/blob/development/server.js#L60) - when would this occur? You're probably going to get an internal server error if you reach this `catch`, which you would respond with a 500 status code. If there is nothing in the database, then you'll probably just get an empty array back - this is repeated in other routes too
* Be sure to always include a `catch()` for a promise in case something goes wrong, like [here](https://github.com/thatPamIAm/build_your_own_be/blob/development/server.js#L66-L67)
* Would like to see the case handle where the [product is not found in the database](https://github.com/thatPamIAm/build_your_own_be/blob/development/server.js#L179)

To get a 3 on this project, you need to score 110 points or higher.

- Points: 140 / 150