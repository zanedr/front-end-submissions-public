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
[BYOB Mountains](https://github.com/tbrandle/mountains_backend_BYOB)

#### Link to the Deployed Application

[BYOB Mountains](https://mountains-api.herokuapp.com/)

Still having issues with this. It passes circleCI, but when you go to the heroku site, you get an error for all of the routes.

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/tbrandle/mountains_backend/commits/master)
This is pointing to a different repo. I had to remake a repo for the one on heroku due to some mistakes I made in the beginning. The old repo has all my commits.

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
Yes

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/db/seeds/dev/mountains.js#L19)

* Why were you proud of this piece of code?

The file seeding took forever to solve, but I think this solution is a clever one. I paired with Brittany to solve it, but walking away, I feel I have a much better understanding of how knex works with promises.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/server.js#L142)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Inside the post mountains end point, I was trying to verify if the range existed in the database.  If it did, send back the id and post the mountain with the foreign id. This part works fine. If the mountain range doesn't exist, I was trying to create the new range, send back the id, then create the new mountain.

For some reason I couldn't get it to work.  I have a feeling it was async issues or just being too nested. Either way, to solve the problem, I simply threw an error.

## Testing

Attach a screenshot or paste the output from your terminal of the result of your test-suite running
[Passing tests](http://recordit.co/3vTFH4bn4B)

## Linting

Attach a screenshot or paste the output from your terminal of the result of your linter running
[Linting image](http://recordit.co/IBJ5kD5fyE)



-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

The only issue with the app currently is that I can't actualy get data back in the deloped heroku URL. Everything is passing, so I'm not sure what is going on there.

-----

# Instructor Feedback

- Points: x / 150
