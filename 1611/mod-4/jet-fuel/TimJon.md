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
(https://github.com/ActionJonny/jet-fuel)

#### Link to the Deployed Application
(https://shorten-your-url-with-us.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

(https://github.com/ActionJonny/jet-fuel/commits/master?author=ActionJonny)

(https://github.com/ActionJonny/jet-fuel/commits/master?author=tbrandle)

#### Provide a Screenshot of your Application
![](http://g.recordit.co/a55Zog1SzR.gif)

## Completion

#### Were you able to complete the base functionality?
* Yes

#### Which extensions, if any, did you complete?

- We were not able to get to neither of the extentions

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
(https://github.com/ActionJonny/jet-fuel/blob/master/server.js)#L28-L40

* We were happy to be able to increment the visits - on the server side - and figure out how to redirect the user in the same get method. We are also pretty happy with our css fade-in/fade-out, and the input animation used for the sidebar.

#### Link to a specific block of your code on Github that you feel not great about
(https://github.com/ActionJonny/jet-fuel/blob/master/public/script.js)#L52-L67

* We did not have a chance to refactor this code block using semantic html.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
![](http://g.recordit.co/zvn4gSIswj.gif)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

* None
-----

#### Please feel free to ask any other questions or make any other statements below!

* We have some, but need to get lunch before gear-up

-----

# Instructor Feedback (Brittany)

### Specification Adherence

**45 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

* Minor Bug: If I type in a new URL `http://google.com`, the redirect is broken because it tries to bring you to `http//google.com`. We should have some URL format validation on the front-end that only allows users to type a URL in a particular format. (Better yet would be to support all the different ways people might type a url.)

* Minor Missing Feature: Users should be able to sort URLs in ascending or descending order. I would expect to be able to double-click the sort buttons and have the sort order reversed, with some sort of visual indicator (up/down arrows?) telling me the current sort.

### User Interface

**15 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

* It's not super clear that the submit button is disabled because you need to select a folder. I would move the folder selection into a more obvious/initial spot to denote that it's the first step before creating a new URL.

* If I type in a URL, then select a folder, I would expect the submit button to be enabled. Instead, the submit button remains disabled until you key into the input field again.

### Data Persistence with SQL Database

**20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

### Testing

**10 points** - Project has server-side happy tests but no sad path tests. Since the server is only handling errors with console.logs, I understand it would've been difficult to implement these. This is something I would definitely go back and try to complete as it will be good practice for future projects this module.

### JavaScript Style

**15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

Nice consistent style and use of ES6. Functions are broken out in a modular way and each have a single responsibility.

I would try to implement [this](https://github.com/ActionJonny/jet-fuel/blob/master/public/script.js#L8) with your `appendFolders` function rather than duplicating that code.

Additionally, when appending elements to the DOM, especially in a loop ([like here](https://github.com/ActionJonny/jet-fuel/blob/master/public/script.js#L13)), you'll want to take advantage of [DocumentFragments](https://developer.mozilla.org/en-US/docs/Web/API/Document/createDocumentFragment). DOM Manipulation is the most expensive part of client-side code, and document fragments allow you to build up all the HTML you need before adding it to directly to the DOM.

Always remember to include a .catch() when working with [promises](https://github.com/ActionJonny/jet-fuel/blob/master/public/script.js#L26-L33).

[This](https://github.com/ActionJonny/jet-fuel/blob/master/public/script.js#L140) is one of those clever one-liners that might read a bit easier if broken out into an `if else`.


### Workflow

**15 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Nice, tiny commits and use of feature branches. Make sure not to commit commented out code or [console.logs](https://github.com/ActionJonny/jet-fuel/blob/master/server.js#L79) to master. You can stash these types of changes with `git create stash` so that you can make a commit without them, but pop them back onto your local copy whenever you need.


## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 135 points or higher

# Final Score: 120 / 150