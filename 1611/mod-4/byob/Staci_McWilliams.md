# BYOB Submission Form
[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.htm)

# Basics

#### Link to the Github Repo for the Project
[Your projects repo URL](https://github.com/stacimcwilliams/build_your_own_backend)

#### Link to the Deployed Application
[Project Production URL](https://go-global-byob.herokuapp.com/)

#### Link to your commits in the github repo for the project
[Staci McWilliams commits](https://github.com/stacimcwilliams/build_your_own_backend/commits/master)

## Completion

* Were you able to complete the base functionality? Yes but would like to write more tests for this project.

* Seeded a database with at least 2 tables and 1 relationship? (Yes)

* Had at least 10 endpoints that returned responses with appropriate status codes? (Yes)

* Secured at least 4 endpoints with JWTs? (Yes)

* Enforced a linter and wrote code that conformed to it? (Yes)

* Wrote tests for both happy and sad paths for each endpoint? (Some)

* Setup automatic deployments with CircleCI to a production app on Heroku? (Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/stacimcwilliams/build_your_own_backend/blob/24aab76e0ce6686bca5656ff71e29db100bb6042/server.js#L172-L183)

* Why were you proud of this piece of code?

I have never completed a patch request before and I was stoked to get this working and implemented in this project.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/stacimcwilliams/build_your_own_backend/blob/24aab76e0ce6686bca5656ff71e29db100bb6042/server.js#L121-L154)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Would like to refactor and dry up this code but did not have the time to do that.

## Testing

![Attach a screenshot or paste the output from your terminal of the result of your test-suite running](http://g.recordit.co/ZUJ5JKM1ib.gif)

## Linting

Attach a screenshot or paste the output from your terminal of the result of your linter running

![Screenshot of terminal output for linting](http://i.imgur.com/0BwJXaB.png)

Please feel free to ask any other questions or make any other statements below!

Thank you for all the help this and understanding my insane allergic reaction on Wednesday night! I feel like I got experience with all the things I didn't work on alone on the last project and it was really beneficial.

Anything else you wanna say!

## Instructor Evaluation Points (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Endpoints

* **60 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params.

### Data Persistence with SQL Database

* **40 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.
* **20 points** - The application persists data in a SQL database but with some incorrect relationships between folders and URLs.
* **0 points** - The application does not persist data in a SQL database.

* That `.DS_Store`...make sure you don't commit [these](https://github.com/stacimcwilliams/build_your_own_backend/tree/master/db)

### Testing & Linting

* **30 points** - Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. The project has a linting configuration that passes with no errors.
* **20 points** - Project has a running test suite that covers most happy and sad paths for each endpoint. Linter has some errors that need fixing.
* **10 points** - Project has significant lack of testing for happy and sad paths of endpoints; Linter is failing on multiple lines.

### JavaScript Style

* **20 points** - Application has exceptionally well-factored code with little or no duplication and all components separated out into logical components. There _zero_ instances where an instructor would recommend taking a different approach.
* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.
* **12 points** - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.
* **5 points** - Your application has a significant amount of duplication and one or more major bugs. Developer cannot speak to most choices and does not know what every line of code is doing.

- Points: x / 150