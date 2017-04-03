# Build Your Own Backend Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[github](https://github.com/mziccardi/byob)

#### Link to the Deployed API
[Your project's production URL](https://byobmz.herokuapp.com/)

## Completion

#### Were you able to complete all 17 endpoints? If not how many did you complete?
* No I was unable to get my patches to work or the 2 custom endponints 

#### Were you able to complete all 34 endpoint tests? If not how many did you complete?
* No I have get and post tests. delete tests are not passing, but delete endpoints work

# Code Quality


* Why were you proud of this piece of code?

There is no code in this project that i'm proud of. I have many of the things working, but I didn't finish the project and not happy about it 

#### Link to a specific block of your code on Github that you feel not great about
[patch](https://github.com/mziccardi/byob/blob/master/server.js#L168-L182)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

After working with multiple people, I know that this patch SHOULD work, but it doesnt and its garbage

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![Imgur](http://i.imgur.com/IuIJxDH.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[Testing body endpoint](https://github.com/mziccardi/byob/blob/master/tests/server-test.js#L78-L99)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

-----

# Instructor Feedback

- Points: 65 / 150

### Endpoints

Do you know what might be happening with your patch endpoints that is causing them to be so problematic?

Notes: 3 Put/Patch endpoints present but broken. 2 Custom endpoints missing

10 points (60 - 10)

### Data Persistence with SQL Database

40 points - The application persists data in a SQL database but with correct relationships between folders and URLs.

### Testing

12 passings tests - 3 tests failing - 19 tests missing

Notes: You can avoid repeating this [before block](https://github.com/mziccardi/byob/blob/master/tests/server-test.js#L48-L59) by having all of your tests wrapped in a top level `describe('Server'...` with that beforeEach in it - that top level will touch all tests

0 points

### JavaScript Style

Notes: All code lives in the server file - server code is much easier to break out, would like to see some logic broken into separate files.

Code formatting is off in multiple places. [See example](https://github.com/mziccardi/byob/blob/master/server.js#L50-L52)

Otherwise, code is in good shape and is using best practices!

15 points - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.
