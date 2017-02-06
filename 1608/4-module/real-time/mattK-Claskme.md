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

# Instructor Feedback (Brittany)

### Concept and Features

Does it have the expected features?

* 45 points - Great job getting all of the base functionality in place. There's a slight bug with the authentication trying to authorize an endpoint as soon as I create a new poll if I'm not logged in. It would be better for this authorization to only occur when trying to actually vote.

### Code Quality (JavaScript)

* 40 points - Developer solves problems with a balance between conciseness and clarity and often extracts logical components. Developer can speak to choices made in the code and knows what every line of code is doing.

You've got a great eye for clever and concise code, and have demonstrated a strong understanding of how to manipulate complex data structures/objects and arrays. 

#### Code That You Like:
Agreed, this is some nice code. Just be consistent in your use of spacing (e.g. [Line 59](https://github.com/MilkMan90/realtime/blob/128f05c63bada45b5ae7a0dc34da93f9d7e56d66/server/server.js#L59) vs [Line 70](https://github.com/MilkMan90/realtime/blob/128f05c63bada45b5ae7a0dc34da93f9d7e56d66/server/server.js#L70)) Add a default linting configuration file at the start of your project and run it before each commit to keep your code clean and consistent.

#### Code that could be refactored:

Agreed, the only thing I would really refactor here is doing the redirect on the server side, sending along a response status of 302. I also would steer clear of committing commented out code. Look into [git stash](https://git-scm.com/docs/git-stash) for hanging onto code you might need later. You can 'stash' your changes away instead of committing them and pop them back onto your local branch whenever you'd like.

### Testing

* 25 points - The application has all routes tested and a minimum of five unit tests. No tests are failing on master and any skipped tests have an explanation of why skipped.


### Workflow

* 20 points - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Lots of good commits but let's clean up the messages a little bit so our history is more informative and consistent. 'code lookin fresh' is hilarious but not super helpful. Also, as mentioned above, get away from the habit of committing commented out code/console.logs. Otherwise your commits look good - small and easy to follow the code changes.

### Extensions

* N/A

## Total Score: 130 / 150