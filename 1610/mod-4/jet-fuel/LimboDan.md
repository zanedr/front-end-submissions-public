# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)


------

# Basics

#### Link to the Github Repository for the Project
[JetFuel](https://github.com/DanGrund/jetFuel/issues/25)

#### Link to the Deployed Application
[heroku deployment calm-temple-36519](https://calm-temple-36519.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Limbo](https://github.com/DanGrund/jetFuel/commits?author=mlimberg)

-[Dan](https://github.com/DanGrund/jetFuel/commits?author=DanGrund)

#### Provide a Screenshot of your Application

![screenshot](http://i.imgur.com/Snyupgi.png)

## Completion

#### Were you able to complete the base functionality?
* Yes 

#### Which extensions, if any, did you complete?

- N/A

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/DanGrund/jetFuel/blob/e77c1e9398192824d4a07c9f20cbd4881a5988be/server.js#L98-L119)

* Why were you proud of this piece of code?

This is the end point for shortened URLs, that handles redirects and visit counter. it's fancy. 

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/DanGrund/jetFuel/blob/e77c1e9398192824d4a07c9f20cbd4881a5988be/db/migrations/20170316143038_initial.js#L14)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

this is the single line in our db that handles the time created for the shortened url. we tried every single knex method for timestamping and couldn't get any of them to work, and Date.now is too big to be an integer in postgres so we ended up just stringifying date.now and storing as a string  ¯\_(ツ)_/¯

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![tests](http://i.imgur.com/9uo3GG7.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

-----

#### Please feel free to ask any other questions or make any other statements below!
Testing the server proved to be difficult because we used a test db in heroku. The beforeEach and AfterEach seemed to be updating the seed records appropriately but then the test to get all folders would say it has a length of 0 instead of 2. Then, when post was added it would successfully push to DB and throw off the get test because it now had length 3 instead of 2. Didn't get it working 100% but we are able to pass tests when we control the # of records in the test DB. 

-----

# Instructor Feedback - Brittany

## Specification Adherence

* 50 points: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.
User Interface
* 20 points - The application is pleasant, logical, and easy to use. There no holes in functionality and the application stands on it own to be used by the instructor without guidance from the developer.
* 15 points - The application has many strong pages/interactions, but a few holes in lesser-used functionality.
* 7 points - The application shows effort in the interface, but the result is not effective. The evaluator has some difficulty using the application when reviewing the features in the user stories.
* 0 points - The application is confusing or difficult to use.

## Data Persistence with SQL Database

* 20 points - The application persists data in a SQL database but with correct relationships between folders and URLs.
* 10 points - The application persists data in a SQL database but with some incorrect relationships between folders and URLs.
* 0 points - The application does not persist data in a SQL database.


## Testing

* 20 points - Project has a running test suite that exercises the application at multiple levels including server and client tests.
* 15 points - Project has a running test suite that tests and multiple levels but fails to cover some features. All controller actions are covered by tests. The application makes some use of integration testing.
* 7 points - Project has sporadic use of tests and multiple levels. Not all controller actions are tested. There are little or no attempts at integration testing.
* 0 points - There is little or no evidence of testing in this application.


## JavaScript Style

* 20 points - Application has exceptionally well-factored code with little or no duplication and all components separated out into logical components. There zero instances where an instructor would recommend taking a different approach.
* 15 points - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.
* 12 points - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.
* 8 points - Your application has a significant amount of duplication and one or more major bugs. Developer cannot speak to most choices and does not know what every line of code is doing.
* 3 point - Your client-side application does not function or the application does not make use of AJAX using jQuery for updating information on the client. Developer writes code with unnecessary variables, operations, or steps which do not increase clarity.
* 0 points - There is little or no client-side code. Developer writes code that is difficult to understand. Application logic shows poor decomposition with too much logic mashed together.

## Workflow

* 20 points - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.
* 15 points - The developer makes a series of small, atomic commits that document the evolution of their application. There are no formatting issues in the code base.
* 7 points - The developer makes large commits covering multiple features that make it difficult for the evaluator to determine the evolution of the application.
* 0 points - The application was not checked into version control.

Points: x / 150
