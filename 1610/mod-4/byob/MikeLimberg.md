# Build Your Own Backend Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

# Basics

#### Link to the Github Repository for the Project
[BYOBackend](https://github.com/mlimberg/BYOBackend)

#### Link to the Deployed API
[BYOBackend production URL](https://byo-backend.herokuapp.com/api/v1/senators)

## Completion

#### Were you able to complete all 17 endpoints? If not how many did you complete?
* Yes

#### Were you able to complete all 34 endpoint tests? If not how many did you complete?
* No - 27 passing

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/mlimberg/BYOBackend/blob/master/server.js#L103-L114)

* Why were you proud of this piece of code?

Most of the code in all of the end points is so similar, but with this endpoint specifically it was great to see how the
server can do some of the heavy lifting and return customized data. 

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/mlimberg/BYOBackend/blob/master/server.js#L27-L39)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Seems like I don't fully understand when catch will in fact work, also don't like the repetitive code. Tried incorporating
the `catch` outside of the if statement but ran into errors.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![test-suite](https://github.com/mlimberg/BYOBackend/blob/master/BYOBackend-tests.jpg)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[Link to code block in repo](https://github.com/mlimberg/BYOBackend/blob/master/test/server.test.js#L258-L266)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

It's not how fast you mow...it's how you mow fast.

-----

# Instructor Feedback

- Points: 118/150

## Endpoints

60 points - The application has all 17 endpoints (6 GETs, 3 POSTs, 3 PUTs/PATCHs, 3 DELETEs, 2 CUSTOM) with responses for happy and sad paths for each endpoint.

## Data Persistence with SQL Database

40 points - The application persists data in a SQL database but with correct relationships between folders and URLs.

## Testing

Note: I'd love to hear what happened with the tests that didn't get written. Was it a time issue, or did you hit a gnarly bug?

0 points (27 of 34 tests)

## JavaScript Style

Watch [things like spacing](https://github.com/mlimberg/BYOBackend/blob/master/test/server.test.js#L43-L46)

In the future, consider breaking out the things that happen in your `.then` and `.catch` into named functions - for example [this logic](https://github.com/mlimberg/BYOBackend/blob/master/server.js#L108-L110) is juicy and already basically wrapped in an anonymous function. And [this code](https://github.com/mlimberg/BYOBackend/blob/master/server.js#L113) gets repeated multiple places and could be DRY'd up.

Those notes aside, you clearly spent a lot of time on cleaning up the code in server.js!

18 points - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.


