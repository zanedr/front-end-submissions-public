# Build Your Own Backend Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

* Fork this repo, if you haven't already and check out a branch
* **Use this README as a template to create a file in this folder with your name as the title.**
* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

# Basics

#### Link to the Github Repository for the Project
[repo](https://github.com/pescel/wtd-api)

#### Link to the Deployed API
[heroku](https://wtd-api.herokuapp.com/users)

## Completion

#### Were you able to complete all 17 endpoints? If not how many did you complete?
 Yes 

#### Were you able to complete all 34 endpoint tests? If not how many did you complete?
 No, 23

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[code](https://github.com/pescel/wtd-api/blob/master/server.js#L77-L90)

* Why were you proud of this piece of code?
I've never made a custom endpoint, so this part of the code was a challenge for me. 

#### Link to a specific block of your code on Github that you feel not great about
[code](https://github.com/pescel/wtd-api/blob/master/tests/server_test.js#L114-L125)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
Some of my tests are too generic and don't test anything specific enough. I struggled through a few tests that get more specific, 
but I just ran out of time to figure it out for all of them. 

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
![](http://i.imgur.com/2N9lzeh.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[example](https://github.com/pescel/wtd-api/blob/master/tests/server_test.js#L212-L220)

-----

#### Please feel free to ask any other questions or make any other statements below!
had a hard time with testing this time around. I had a lot of problems with tests because my db wasn't being cleared out. Is there something
I can do to get that to clear on it's own or should I have installed something?
-----

# Instructor Feedback

- Points: 115 / 150 (3)

Notes: With the DB being cleared out - there's nothing to install but you do need to manually clear out - check out some of the other project repos or ask classmates on how they handled it. For the most part, everyone seems to have gone with a similar solution and it's a reasonable one!

Great README!

Watch your spacing in files like your [initial migration](https://github.com/pescel/wtd-api/blob/master/db/migrations/20170321195542_initial_db_setup.js) - this file is still just JavaScript, so you should lint this file too.

OMG Jenny Slate is the BEST!

## Endpoints

60 points - The application has all 17 endpoints (6 GETs, 3 POSTs, 3 PUTs/PATCHs, 3 DELETEs, 2 CUSTOM) with responses for happy and sad paths for each endpoint.

## Data Persistence with SQL Database

40 points - The application persists data in a SQL database but with correct relationships between folders and URLs.

## Testing

Good job on the testing - Seems like the inability to clear the database prevented you from doing as much in depth as you wanted to - so consider the solution above of asking how others cleared. The solution is a lot lower level than you might think.

23/34

0 points - Project has a running test suite that has 34 passing tests (a sad path and a happy path test for each endpoint)

## JavaScript Style

You can wrap the results of `.catch` and `.then` into named functions to refactor your code. For example, [this](https://github.com/pescel/wtd-api/blob/master/server.js#L59) is repeated often in your code.

15 points - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

