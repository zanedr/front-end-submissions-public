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
[Your projects's repo URL](https://github.com/ejwill04/byob)

#### Link to the Deployed API
[Your project's production URL](https://build-your-own-backend.herokuapp.com/)

## Completion

#### Were you able to complete all 17 endpoints? If not how many did you complete?
* Yes

#### Were you able to complete all 34 endpoint tests? If not how many did you complete?
* Yes.  There are 38 tests.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/ejwill04/byob/blob/master/test/server-test.js#L405-L501)

* Why were you proud of this piece of code?

I'm testing a PUT endpoint in this bit of code.  The endpoint should only update what the user passes to the endpoint.  So, if a user passes all three params, it would update all of them.  If they don't pass any params, nothing gets updated.  

In order to check on what was updated, I first made GET requests, stored the repsonse in a local variable, and then compared the PUT response to these local variables.  

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/ejwill04/byob/blob/master/server.js#L36-L57)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

The nested IF statements aren't pretty, but they get the job done.  

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![Test Screenshot](http://i.imgur.com/QoMyQEz.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[Testing body params in PUT endpoint (as described in Proud code section)](https://github.com/ejwill04/byob/blob/master/test/server-test.js#L405-L501)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

-----

# Instructor Feedback

- Points: x / 150
