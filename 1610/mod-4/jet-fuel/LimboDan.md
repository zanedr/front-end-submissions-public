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

# Instructor Feedback

- Points: x / 150
