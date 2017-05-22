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

# Instructor Feedback

- Points: x / 150
