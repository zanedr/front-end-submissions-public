# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

* Fork this repo, if you haven't already and check out a branch
* Use this README as a template to create a file in this folder with your name as the title.
* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

# Basics

#### Link to the Github Repository for the Project
[Your projects's repo URL](https://github.com/noahpeden/jet-fuel)

#### Link to the Deployed Application
[Your project's production URL](https://jet-fuel-np.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Noah](https://github.com/noahpeden/jet-fuel/commits/master)

-[Dylan](https://github.com/noahpeden/jet-fuel/commits/master)

#### Provide a Screenshot of your Application
http://imgur.com/a/XxlEt

## Completion

#### Were you able to complete the base functionality?
* Yes

#### Which extensions, if any, did you complete?

-  N/A

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/noahpeden/jet-fuel/blob/master/server.js)

* Why were you proud of this piece of code?

Cause it's our first truly backend server side code.
And also because we learned and used Knex syntax.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/noahpeden/jet-fuel/blob/master/public/app.js)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Still need to refactor into smaller functions such as moving axios to be a dynamic call.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
http://imgur.com/a/Jv8zW

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'
None, we had a lot of trouble trying to set up our unit tests as we couldn't figure out how to get past the jquery not defined error that we were getting. 
-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

-----

# Instructor Feedback

## Instructor Evaluation Points

The following set of points are distributed at the discretion of the instructor.

### Specification Adherence

* **50 points**: All functionality was met.

### User Interface

* **15 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

Overall, the application is well structured with the following exceptions:

* The list of URLS could be better. The sorting buttons should be on top because if you have a long list of urls you have to scroll a long ways down to sort. Also, make the URLs info more spaced out and on a different background. It's tough to read the short url.

### Data Persistence with SQL Database

* **20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

### Testing

* **7 points** - Project has sporadic use of tests and multiple levels. Not all controller actions are tested. There are little or no attempts at integration testing.

There are 3 passing server-side tests and 1 failing test. There is an attempt at unit testing but no passing unit tests. 

### JavaScript Style

* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

The code is well broken out into small functions and consistent style, but there are areas of improvement:

* I would have liked to seen the code written in ES6
* Remove any unused global variables (var $shortUrl = $('.short-url'))

### Workflow

* **20 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Lots of small, atomic commits and good conversations in PRs.

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 135 points or higher

# Final Score: 127 / 150

