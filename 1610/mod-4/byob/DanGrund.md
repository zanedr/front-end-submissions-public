# Build Your Own Backend Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[Your projects's repo URL](https://github.com/DanGrund/build-your-own-backend)

#### Link to the Deployed API
[Your project's production URL](https://byob-dan1.herokuapp.com/)
example <code>GET</code> request
[/api/v1/users](https://byob-dan1.herokuapp.com/api/v1/users)

## Completion

#### Were you able to complete all 17 endpoints? If not how many did you complete?
* Yes

#### Were you able to complete all 34 endpoint tests? If not how many did you complete?
* Yes, though just 31.. 
no bad get <code>/path</code> requests per slack channel, which takes it down from 34 to 31. all other paths have HAPPY & SAD tests

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/DanGrund/build-your-own-backend/blob/3e7c585cbe0626c3cb51579085e76caef9cd8e73/test/server-test.js#L53-L75)

* Why were you proud of this piece of code?
honestly just being able to write my first passing server test for this was really exciting! I think there are better tests, I know that some of my others actually revealed fixable errors in my code which is a fantastic feeling, but this was the first.. so yeah!


Reason you are proud of code

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/DanGrund/build-your-own-backend/blob/3e7c585cbe0626c3cb51579085e76caef9cd8e73/server.js#L38-L71)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

I nested a .then inside a .then inside a .then to gather user info from three different tables. I'm trying to figure out how to use the .join methods knex and postgres offer to more cleanly factor this code block. 

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![passing-tests-screenshot](http://i.imgur.com/c7lZroW.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[POST to an unknown composition](https://github.com/DanGrund/build-your-own-backend/blob/c47eceed787ef8e54dc68fd06fe9348c63ec3ea4/test/server-test.js#L243-L255)
-----

#### Please feel free to ask any other questions or make any other statements below!

This was a lot of fun, I'm looking forward to implement this as soon as possible in my front-end application!
will fill out the last rubric requirement, speaking to the JSON API standards in my readme, PRed by monday, but feel free to grade now!
-----


# Instructor Feedback - Brittany

## Endpoints

60 points - Found 17 endpoints: 7 GETs, 3 POSTs, 3 PATCHes, 4 DELETEs


## Data Persistence with SQL Database

40 points - The application persists data in a SQL database but with correct relationships between folders and URLs.

## Testing

30 points - Project has a running test suite that has 34 passing tests (a sad path and a happy path test for each endpoint)


## JavaScript Style

15 points - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

Some Inconsistent [use of ES5 vs ES6](https://github.com/DanGrund/build-your-own-backend/blob/master/server.js#L27-L30)

I'd send an error object back to the client along with your status in your [catch blocks](https://github.com/DanGrund/build-your-own-backend/blob/master/server.js#L30-L34) rather than just console.logging to your terminal.

[This](https://github.com/DanGrund/build-your-own-backend/blob/master/server.js#L40) should be a `let` rather than a `const` since you are manipulating it later on.

Usually if you're returning an erroneous status code you'd want to send an error object rather than just an empty array [here](https://github.com/DanGrund/build-your-own-backend/blob/master/server.js#L79)

Proper status code for a successful creation is 201 rather than [200](https://github.com/DanGrund/build-your-own-backend/blob/master/server.js#L85)



- Points: 145/150
