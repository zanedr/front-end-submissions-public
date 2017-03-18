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
[gh](https://github.com/jksmall0631/jet-fuel)

#### Link to the Deployed Application
[heroku](https://jet-fuelz.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project


#### Provide a Screenshot of your Application

!(http://i.imgur.com/gvKtfVM.png)

## Completion

#### Were you able to complete the base functionality?
* Yes

#### Which extensions, if any, did you complete?

N/A

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[code](https://github.com/jksmall0631/jet-fuel/blob/master/server.js#L121-L132)

* Why were you proud of this piece of code?

Proud because it was a much larger block of code and got refactored to look much better.

#### Link to a specific block of your code on Github that you feel not great about
[code](https://github.com/jksmall0631/jet-fuel/blob/master/public/app.js#L74-L85)


* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Not happy with this because we didn't have time to break it out and refactor. 

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
We ran out of time with unit testing, and had a hard time understanding what we could test. We also had all server tests passing and realized last minute that we needed to create a testing db. Started going through the blog that was linked in the lesson but ran out of time to implement the whole thing. 

![](http://i.imgur.com/E6jfQgM.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

-----

#### Please feel free to ask any other questions or make any other statements below!

Meeka - Remember last mod when I was having CORS issues with my assessment? It came back to haunt me this project too! For a good portion of the project I wasn't able to push up code because I was getting issues with the database. Is there anything I can do to fix it?? 
                        -love, Lauren

-----

# Instructor Feedback - Brittany

## Specification Adherence

* 45 points: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

The shortened URL breaks if I use the format `http://google.com` or even if I use `http://www.google.com` when I first enter a URL. (Trying to access it from the shortened URL will actually bring me to `http://http//google.com`). I'd like to see either an error message pop-up or some sort of invalidator if I enter a URL that does not fit the correct format. Better yet, I'd like to be able to enter URLs in any of these three formats:

* http://google.com
* http://www.google.com
* www.google.com

Currently, it appears only the last format is supported.


## User Interface
* 17 points - The application is pleasant, logical, and easy to use. There no holes in functionality and the application stands on it own to be used by the instructor without guidance from the developer.

One nitpick with the sorting - I'd like to only have a single button that toggles between an up/down arrow rather than two separate buttons for each. The most common convention is to just flip the icon/sort indicator vertically to point up or down depending on the current sort order. Many people are used to just being able to toggle from the same button rather than using two separate arrows.

## Data Persistence with SQL Database

* 20 points - The application persists data in a SQL database but with correct relationships between folders and URLs.

## Testing

* 7 points - Project has sporadic use of tests and multiple levels. Not all controller actions are tested. There are little or no attempts at integration testing.

## JavaScript Style

* 12 points - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.

Is there a reason we're using == instead of === [?](https://github.com/jksmall0631/jet-fuel/commit/a01c3bad3aec86e28115d6162a76c0214d75f7ef#diff-4fb0e45f4ba6881335591c2d8331b72bR66)

I'd make this endpoint [param](https://github.com/jksmall0631/jet-fuel/blob/master/server.js#L28) a little clearer than just 'id'. It's tough to tell what it should be doing based on the endpoint alone. I'd rename that param to something like `:shortenedUrlId` to give a little more context about what a user is trying to hit.

Lots of toggling between [ES5](https://github.com/jksmall0631/jet-fuel/blob/master/server.js#L31) and [ES6](https://github.com/jksmall0631/jet-fuel/blob/master/server.js#L45) syntax. Let's be consistent.

[Noooooo](https://github.com/jksmall0631/jet-fuel/blob/master/server.js#L34)

When doing a `POST` to [create a new record](https://github.com/jksmall0631/jet-fuel/blob/master/server.js#L63), the status code should be 201 rather than 200 if things were successful. Take a look at all the status codes that exist [here](http://www.restapitutorial.com/httpstatuscodes.html).

Nitpick: I would reorder [these request handlers](https://github.com/jksmall0631/jet-fuel/blob/master/server.js#L72-L119) so that you keep the endpoints together. e.g. it reads a little more smoothly if we know all the types of requests we can make to a particular endpoint. I'd reorder them like so:

* app.get('/api/folders/')
* app.post('/api/folders/')
* app.get('/api/folders/:folderId')
* app.post('/api/folders/:folderId')


Also, you seem to have two different handlers for POST to /api/folders. [Here](https://github.com/jksmall0631/jet-fuel/blob/master/server.js#L55) and [here](https://github.com/jksmall0631/jet-fuel/blob/master/server.js#L83).


## Workflow

* 15 points - The developer makes a series of small, atomic commits that document the evolution of their application. There are no formatting issues in the code base.

Ahhh don't commit large blocks of [commented out code](https://github.com/jksmall0631/jet-fuel/blob/master/server.js#L133-L148) and definitely no [console.logs](https://github.com/jksmall0631/jet-fuel/commit/b4b9e6ae00ef9f922d110791414c427dd360a184#diff-78c12f5adc1848d13b1c6f07055d996eR51)

Also, in the same vein, make sure you remove things you're no longer using. I was slightly confused that you still had folders and urls in your [app.locals](https://github.com/jksmall0631/jet-fuel/blob/master/server.js#L19-L20) even though you had switched over to using a database.

Some commits are a little long, and contain changes that should be broken out into a different commit with a different message. [For example](https://github.com/jksmall0631/jet-fuel/commit/a01c3bad3aec86e28115d6162a76c0214d75f7ef), the addition of all the semi-colons here (I'm assuming this was a linting fix), should be broken out into a separate commit named 'Fix Linting Errors'. You can control what gets put into a particular commit by using `git add --patch` rather than adding everything all at once, it will show you each little change you've made and allow you to commit them in chunks.

Points: 116 / 150
