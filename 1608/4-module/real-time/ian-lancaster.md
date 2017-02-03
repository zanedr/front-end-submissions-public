# Real Time Submission Form

[Project Spec](http://frontend.turing.io/projects/real-time.html)

* Fork this repo, if you haven't already and check out a branch
* Use this README as a template to create a file in this folder with your name as the title.
* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

# Basics

#### Link to the Github Repository for the Project`
[Project Repo](https://github.com/ianlancaster/real-time-polling)

#### Link to the Deployed Application
[Live Deployment](https://real-time-polling-il.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[TeamMate1](https://github.com/ianlancaster/real-time-polling/commits/master)

#### Provide a Screenshot of your Application
![pollApp](https://github.com/ianlancaster/real-time-polling/blob/master/application-screenshot.png?raw=true)

## Completion

#### Were you able to complete the base functionality?
* Yes this application covers all base functionality

#### Which extensions, if any, did you complete?
* I did not complete either of the extensions

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
- [Express POST Testing](https://github.com/ianlancaster/real-time-polling/blob/master/test/index.js#L111-L127)
* I am proud of this code because I was able to figure out how to use supertest and chai together to write a very robust test for the post route with minimal lines.

#### Link to a specific block of your code on Github that you feel not great about
* I wrote and refactored the code as best I can. There is nothing that I can find that I would want to change. I wish I had done the extensions.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
![Testing Screenshot](https://github.com/ianlancaster/real-time-polling/blob/master/test-screenshot.png?raw=true)

Unit testing the script files proved impossible without incorporating webpack. jquery is currently loaded via cdn and without loading that script first jquery is undefined in tests. I tried imports, requires, binding, etc.. could not make it work. The server is thoroughly tested though.

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[Testing an unhappy path](https://github.com/ianlancaster/real-time-polling/blob/master/test/index.js#L147-L162)

This tests that express returns an error if a user has an incomplete profile. This functionality makes it a little bit harder to bypass the authentication.

-----

#### Please feel free to ask any other questions or make any other statements below!

It was really hard to get the authentication to work without using query parameters. I could not whitelist wildcard callback URLs, so I had to set up a detour redirect to the login route in order to authenticate. I would love some feedback on in this area. Is this a good way of handling auth?

-----

# Instructor Feedback

- Points: (base 150)
