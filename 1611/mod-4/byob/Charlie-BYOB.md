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
[Your projects's repo URL](https://github.com/dunncl15/BYOB)

#### Link to the Deployed Application
[Your project's production URL](https://byob-prod.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/dunncl15/BYOB/commits/master)

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
[Link to code block in repo](https://github.com/dunncl15/BYOB/blob/master/server.js#L48-L63)

* Why were you proud of this piece of code?
I thought using .some was a good way to approach validating that a PATCH request has at least one of the required park properties. If someone tries a PATCH with an arbitrary property that is not listed in parkProps then it will throw an error.

However, it still fails when you submit a PATCH with multiple properties and at least one property is included in the parkProps array. Ex/

{ name: 'New Park',
  mumbo_jumbo: 'adfadf' }

This error isn't caught because the .some recognizes the name property so the condition is met.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/dunncl15/BYOB/blob/master/db/seeds/dev/locations.js#L21-L28)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Promises are still a bit confusing to me. I have a hard time following when a Promise is resolved and this particular code block is confusing from that stand point.

## Testing

Attach a screenshot or paste the output from your terminal of the result of your test-suite running
![](http://i.imgur.com/wbLfUQ0.png)

## Linting

Attach a screenshot or paste the output from your terminal of the result of your linter running
![](http://i.imgur.com/PnnHnBt.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Thanks for your help this week!

-----

# Instructor Feedback

- Points: x / 150
