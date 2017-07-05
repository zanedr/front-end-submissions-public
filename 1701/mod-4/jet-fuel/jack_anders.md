# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

# Basics

#### Link to the Github Repository for the Project
[jetfuel](https://github.com/anderswood/jetfuel)

#### Link to the Deployed Application
[heroku](https://aw-jb-jetfuel.herokuapp.com/)

#### Provide a Screenshot of your Application
![screenshot](https://github.com/anderswood/jetfuel/blob/master/public/images/app_screenshot.png)

## Completion

#### Were you able to complete the base functionality?
Yes.

#### Which extensions, if any, did you complete?
None... it looks nice?

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/anderswood/jetfuel/blob/master/public/javascript.js#L87-L102)

* Why were you proud of this piece of code?

This sort function consolidates a lot of the sorting functionality into a few, slick lines.

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/anderswood/jetfuel/blob/master/public/helper.js#L1-L18)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

The code is very coupled/nested and therefore hard to follow, debug and test. It was really challenging to get it to work in the first place so that was the focus of creating the block.  

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![test suite](https://github.com/anderswood/jetfuel/blob/master/public/images/test_results.png)

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

Loved the emphasis on the UI

-----


# Instructor Feedback (Brittany)

## Specification Adherence

**50 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

## User Interface

**17 points**: The application is pleasant, logical, and easy to use. There no holes in functionality and the application stands on it own to be used by the instructor without guidance from the developer.

* I can't really tell what's happening when I enter an invalid URL. Sometimes it looks like it works and goes through anyway, and then the link redirect is just broken, other times it looks like nothing happens but I also don't get any user feedback or error handling that tells me so.

## Data Persistence with SQL Database

**20 points**:  The application persists data in a SQL database with correct relationships between folders and URLs.

## Testing

**10 points**: Project has a running test suite that tests at multiple levels but fails to cover some features.

* No client-side tests but good coverage of happy/sad paths on server-side routes.

* You never want to [rollback](https://github.com/anderswood/jetfuel/blob/master/tests/routes.spec.js#L37) your database during tests. That would potentially put your schema in an out-of-date state and you'd be testing against the wrong data structure. You're essentially undo-ing the rollback right away by calling `migrate.latest` on line [39](https://github.com/anderswood/jetfuel/blob/master/tests/routes.spec.js#L39) so what good is this doing you anyway?

* I'd pick a less confusing sad [endpoint](https://github.com/anderswood/jetfuel/blob/master/tests/routes.spec.js#L68) for this test. It sounds like it could be a legitimate endpoint.

## JavaScript Style

**x points**: Lorem ipsum dolor set amet

## Workflow

**12 points**: The developer makes a series of small, atomic commits that document the evolution of their application. There are some formatting issues in the code base and some commits are handling more than they should be.

* There are a lot of [duplicate](https://github.com/anderswood/jetfuel/commit/1a5d4a048a7cd2ce879c4711c5d1c6865dfed191) [commit](https://github.com/anderswood/jetfuel/commit/c42cc34ff58d6626cf8e176bb178108250f582b6) messages in [your](https://github.com/anderswood/jetfuel/commit/52b9ba470092f6838e76fcf5c995ad5d052fd6b4) [history](https://github.com/anderswood/jetfuel/commit/da21a19ed59fd6ae0bd1f6489cb9ab11019ccea4) that make it hard to recognize what changes are being made where. Not all of the logic in each commit maps well to its message. There are irrelevant/unrelated changes.

* Console.logs and commented out code have been committed to master and shouldn't be. Use `git stash` or `git add --patch` to avoid committing those to master.


### To get a 3 on this project, you need to score 110 points or higher
### To get a 4 on this project, you need to score 135 points or higher

# Final Score: x / 150
