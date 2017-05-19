# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

* Fork this repo, if you haven't already and check out a branch
* Use this README as a template to create a file in this folder with your name as the title.
* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

# Basics

#### Link to the Github Repository for the Project
[BYOB Mountains](https://github.com/tbrandle/mountains_backend/tree/master/turing/mod-4-projects/BYOB-mountains)

#### Link to the Deployed Application

Couldn't get the project deployed. I'm having trouble with my eslinter not recognizing the mocha syntax in my testing files.

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/tbrandle/mountains_backend/commits/master)

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
No

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/tbrandle/mountains_backend/blob/master/turing/mod-4-projects/BYOB-mountains/db/seeds/dev/mountains.js#L19)

* Why were you proud of this piece of code?

The file seeding took forever to solve, but I think this solution is a clever one. I paired with Brittany to solve it, but walking away, I feel I have a much better understanding of how knex works with promises.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/tbrandle/mountains_backend/blob/master/turing/mod-4-projects/BYOB-mountains/server.js#L141)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Inside the post mountains end point, I was trying to verify if the range existed in the database.  If it did, send back the id and post the mountain with the foreign id. This part works fine. If the mountain range doesn't exist, I was trying to create the new range, send back the id, then create the new mountain.

For some reason I couldn't get it to work.  I have a feeling it was async issues or just being too nested. Either way, to solve the problem, I simply threw an error.

## Testing

Attach a screenshot or paste the output from your terminal of the result of your test-suite running
[Passing tests](http://recordit.co/3vTFH4bn4B)

## Linting

Attach a screenshot or paste the output from your terminal of the result of your linter running
[Linting image](http://imgur.com/eIuG7p6)



-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

I had some very strange issues with eslint and my testing suite. That was the only thing keeping me from deploying. Everything else on circleCI seems to be set up correctly, but it wont let me deploy with the error in the test.  I found a snippet of code for eslint to ignore the testing suite, but it won't work if it is commented out.  If I un comment the line, all my testing errors go away except for the snippet itself.

-----

# Instructor Feedback

- Points: x / 150
