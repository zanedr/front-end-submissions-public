# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[Your projects's repo URL](https://github.com/esayler/byob)

#### Link to the Deployed Application
[Your project's production URL](https://zelda-recipes.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/esayler/byob/commits/master)

## Completion

#### Were you able to complete the base functionality?

* Seeded a database with at least 2 tables and 1 relationship?
(Yes)

* Had at least 10 endpoints that returned responses with appropriate status codes?
(Yes)

* Secured at least 4 endpoints with JWTs?
(Yes)

* Enforced a linter and wrote code that conformed to it?
(Yes)

* Wrote tests for both happy and sad paths for each endpoint?
(Yes)

* Setup automatic deployments with CircleCI to a production app on Heroku?
(Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/esayler/byob/blob/master/server/router.js#L254)

* Why were you proud of this piece of code?
- Used a transaction to make sure mutiple inserts of data are committed and if any fail then all changes to the DB are rolled back.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/esayler/byob/blob/master/server/router.js#L302)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

- Lots of repetive code. Could refactor using knex's `.modify()` 

## Testing

![](http://i.imgur.com/2wUjAPK.png)

## Linting

![](http://i.imgur.com/wLHR6bb.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

**Updates:**

1. Add happy and sad path tests for all endpoints
2. Deploy to Heroku
3. Set up CircleCI and auto deployments to Heroku
4. Secure all POST/PATCH/DELETE endpoints with JWTs
5. Added query param support to filter `/materials` endpoint by attribute


-----

## Instructor Evaluation Points (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Endpoints

* **60 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params.
* **40 points** - Developer has implemented all 10 endpoints but did not secure 4 of them with JWTs or have a custom endpoint based on query params.
* **20 points** - Developer is missing endpoints and has not secured or customized any of the ones that have been implemented.

### Data Persistence with SQL Database

* **40 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.
* **20 points** - The application persists data in a SQL database but with some incorrect relationships between folders and URLs.
* **0 points** - The application does not persist data in a SQL database.

### Testing & Linting

* **30 points** - Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. The project has a linting configuration that passes with no errors.
* **20 points** - Project has a running test suite that covers most happy and sad paths for each endpoint. Linter has some errors that need fixing.
* **10 points** - Project has significant lack of testing for happy and sad paths of endpoints; Linter is failing on multiple lines.

### JavaScript Style

* **20 points** - Application has exceptionally well-factored code with little or no duplication and all components separated out into logical components. There _zero_ instances where an instructor would recommend taking a different approach.
* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.
* **12 points** - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.
* **5 points** - Your application has a significant amount of duplication and one or more major bugs. Developer cannot speak to most choices and does not know what every line of code is doing.

To get a 3 on this project, you need to score 110 points or higher.

- Points: x / 150