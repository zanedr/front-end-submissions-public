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

#### Link to the Github Repository for the Project
[Real Time](https://github.com/MilkMan90/realtime)

#### Link to the Deployed Application
[Clask Me Anything](https://claskmeanything.herokuapp.com)

#### Link to Your Commits in the Github Repository for the Project

-[Matt](https://github.com/MilkMan90/realtime/commits/master)

#### Provide a Screenshot of your Application
![Gif](http://g.recordit.co/I4wFEadK4D.gif)

## Completion

#### Were you able to complete the base functionality?

* Yep!

#### Which extensions, if any, did you complete?

No extensions completed at time of official due date, but the functions were refactored as such to allow for easy addition of a database. Also added a date time input field but it doesn't work right now....

# Code Quality

#### Link to a specific block of your code on Github that you are proud of

[Update Vote Code](https://github.com/MilkMan90/realtime/blob/128f05c63bada45b5ae7a0dc34da93f9d7e56d66/server/server.js#L58-L71)

* Why were you proud of this piece of code?


I think this code, while not perfect, does a good job of updating the data structure efficiently using sweet prototype functions to make it easy!

#### Link to a specific block of your code on Github that you feel not great about
* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

[Reroute Code](https://github.com/MilkMan90/realtime/blob/128f05c63bada45b5ae7a0dc34da93f9d7e56d66/src/scripts/index.js#L20-L48)

I don't feel awesome about this because I think the actual redirect should be happening on the server side, not the client side. Given more time, I think id switch this code over to redirect on the server side.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

```
GET /api/poll/:pollid
   ✓ should return a poll (40ms)

 POST /api/newpoll
   ✓ should create a new poll (43ms)

 url param function
   ✓ should return the correct parameter number
   ✓ should return the correct parameter - string
   ✓ should NOT return the correct parameter - string

 database tester
   ✓ get initial pool index should return 0
   ✓ should successfull add a poll to the database and return a new index
   ✓ get pool index should return 1
```

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

I didn't get that deep with my testing
-----

#### Please feel free to ask any other questions or make any other statements below!

Before the end of the mod I plan to implement the psql db!
-----

# Instructor Feedback

- Points: (base 150)
