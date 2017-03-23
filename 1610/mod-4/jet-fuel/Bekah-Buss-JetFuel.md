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
[JetFuel](https://github.com/turingschool/front-end-submissions-public/tree/master/1610/mod-4/jet-fuel)

#### Link to the Deployed Application
[Heroku link](https://jetfuel-mod4.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Jeff Buss](https://github.com/JeffBuss/jet-fuel/commits?author=JeffBuss)

-[Bekah Lundy](https://github.com/JeffBuss/jet-fuel/commits?author=bekahlundy)

#### Provide a Screenshot of your Application

[Screenshot](https://gyazo.com/32f393c9c2ed6f67a076382a5e85dcb8)

## Completion

#### Were you able to complete the base functionality?
* Yes - functionality is now all working

#### Which extensions, if any, did you complete?

* None

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[displayFolders](https://github.com/JeffBuss/jet-fuel/blob/master/public/app/app.js#L69)

* Why were you proud of this piece of code?

It's the heart of our project! Displays all the pretty folders using our good friends jquery and map!

#### Link to a specific block of your code on Github that you feel not great about
[updateClicks](https://github.com/JeffBuss/jet-fuel/blob/master/public/app/app.js#L116)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

I think we now feel good about the code, we got it all done this weekend. We haven't looked into refactoring too much yet.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[Screenshot](https://gyazo.com/6c6784e3de3e9f063f26330c39f67869)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

* I beleive Jeff was having trouble with the one of the tests, I am not sure which one. I'll have him update this pr if needed

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

-----

# Instructor Feedback

## Instructor Evaluation Points

The following set of points are distributed at the discretion of the instructor.

### Specification Adherence

* **40 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

All functionality was met except for the following:
* Copy/paste of short urls doesn't correctly redirect (http://http//www.espn.com)


### User Interface

* **18 points** - The application is pleasant, logical, and easy to use. There no holes in functionality and the application stands on it own to be used by the instructor _without_ guidance from the developer.

Really clean UI, easy to use. The only improvement I would make would be to format the created date to be more human readable and to make the URL table more spaced out. 

### Data Persistence with SQL Database

* **20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

### Testing

* **12 points** - Project has sporadic use of tests and multiple levels. Not all controller actions are tested. There are little or no attempts at integration testing.

All endpoints are tested with a test db but no unit tests.

### JavaScript Style

* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

Lots of good, small functions that are consistently written with ES6. I would have liked to seen better error handling on the server side with the correct status code being returned based on the error. Also, this hot mess of an if statement should have been refactored:

```js
  .then((response) => {
    if (filter === 'up') {
      response = filterPop(response, filter)
    } else if (filter === 'down') {
      response = filterPop(response, filter)
    } else if (filter === 'dUp') {
      response = filterDate(response, filter)
    } else if (filter === 'dDown'){
      response = filterDate(response, filter)
    } else {
      displayUrls(response)
    }
    displayUrls(response)
  })
  }
}
```

### Workflow

* **20 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Lots of commits, lots of branches, good conversations.

## Projects are due on Friday 3/17, 12:00 p.m. We will provide a submission form for all teams to submit their repos.

## Project is worth 150 points with 15 extra points possible

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 135 points or higher

# Final Score: 125 / 150
