# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

# Basics

#### Link to the Github Repository for the Project
[jetfuel](https://github.com/jennPeavler/jetFuel)

#### Link to the Deployed Application
[a.shrtee.co](http://a.shrtee.co/)

#### Provide a Screenshot of your Application
![screenshot](https://drive.google.com/open?id=0B3ItQVupdvvgbHk1cWdYRXp4aHM)

## Completion

#### Were you able to complete the base functionality?

We were able to complete all functionality excepting entirely completing the sort functionality.  We did get popularity sort working on first click, but ran out of time to finish that part of functionality.
We were also short on time to dry up code, so there is a lot of clean up that still needs to be done, including taking out some areas where code is a bit more hard-coded that ideal.


#### Which extensions, if any, did you complete?

N/A, no extensions provided

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[server happy code](https://github.com/jennPeavler/jetFuel/blob/master/server/server.js#L1-L24)
[router happy code](https://github.com/jennPeavler/jetFuel/blob/master/server/router.js#L1-L11)
[api functions happy code](https://github.com/jennPeavler/jetFuel/blob/master/server/api.js#L1-L99)

We were really happy about setting up our server using the router and breaking out the functions into a separate file.
Thought the code looked really clean and easy to follow.

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/jennPeavler/jetFuel/blob/master/client/assets/scripts/script.js#L33-L198)

Well, are you kidding, of course I'm sad about this, it's a 170 line function!  We know how to dry up this code we just
ran out of time.  Using vanilla was particularily challenging because we had to use so many extra lines for to generate our css within our javascript....

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](https://drive.google.com/open?id=0B3ItQVupdvvgQUU0MGdRUndQSkE)

We are testing happy paths on all of our requests, and sand paths on a few.  We ran out of time to do all sad paths.  We also did not get to client side testing....

#### Please feel free to ask any other questions or make any other statements below!

Comment from Jenn Peavler:  Why the mandate to use vanilla or JQuery?  I spent a lot of time de-rustifying my vanilla and I thought that
detracted from the time I spent exploring server/client server/database interactions.  One solution would be in the prework to mod4, 
tell students to refresh on their vanilla/jQuery skills so that there's not so much struggle with those basics.

Other than that, thanks!  I learned a lot through this project.

Comment from Devon Bull:  Wanted to have a more complete lesson on how to set up testing database.

-----


# Instructor Feedback (Brittany)

## Specification Adherence

**48 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

* I can't actually see the date created or the visit count on the UI anywhere so it's difficult to tell from a user perspective whether the sorting functionality is accurate or not.

## User Interface

**15 points**: The application has many strong pages/interactions, but a few holes in lesser-used functionality.

* Using alert messages for error handling is a really out-dated and painful method for the user. When I enter an incorrect URL, I'd rather get a notification at the top of the screen with an error message rather than have to click out of an alert box.

* I can't see the date added or visit count for URLs and there is no visual indicator for what the sort order is of URLs at any given moment.

## Testing

**10 points**: Project has a running test suite that tests at multiple levels but fails to cover some features.

* No client-side tests but good coverage of happy/sad paths on server-side routes.

* You never want to [rollback](https://github.com/jennPeavler/jetFuel/blob/master/test/routes.spec.js#L28-L30) your database during tests. That would potentially put your schema in an out-of-date state and you'd be testing against the wrong data structure. You're essentially undo-ing the rollback right away by calling `migrate.latest` on line 30, so what good is this doing you anyway?

* [No](https://github.com/jennPeavler/jetFuel/blob/8b3e1ca5108aef731355ade3b4f2a947bb158e03/test/routes.spec.js#L86-L89)

## JavaScript Style

**x points**: Lorem ipsum dolor set amet

## Workflow

**12 points**: The developer makes a series of small, atomic commits that document the evolution of their application. There are some formatting issues in the code base and some commits are handling more than they should be.

* Committed some commented out code and console.logs throughout the history

* Some commits have fairly large changesets with unrelated [changes](https://github.com/jennPeavler/jetFuel/commit/93c99ac5d6afb98d2a7f8d511afcf827912cb1f6). Split these things out into separate commits rather than lumping them into a general 'refactor' commit.

### To get a 3 on this project, you need to score 110 points or higher
### To get a 4 on this project, you need to score 135 points or higher

# Final Score: x / 150
