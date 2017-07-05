# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

# Basics

#### Link to the Github Repository for the Project
[JetFuel GitHub](https://github.com/Adamj1232/Jet-Fuel)

#### Link to the Deployed Application
[JetFuel Heroku](https://jet--fuel.herokuapp.com/)

#### Provide a Screenshot of your Application
![Screenshot](https://imgur.com/a/kRgx4)

## Completion

#### Were you able to complete the base functionality?

Functionality should(hopefully) meet specifications.

#### Which extensions, if any, did you complete?

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Vanilla construction](https://github.com/Adamj1232/Jet-Fuel/blob/master/public/links.js)

* Why were you proud of this piece of code?
Proud might not be the right word. More in awe of how people ever built intricate websites with pure vanilla JS, and grateful we don't have to do that.

#### Link to a specific block of your code on Github that you feel not great about
[The whole server](https://github.com/Adamj1232/Jet-Fuel/blob/master/server.js)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
Nothing that experience and time won't fix.  It's still new, and feel like it can be done better.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](https://imgur.com/a/1W2ru)

#### Please feel free to ask any other questions or make any other statements below!

this hard. brain hurt.

-----


# Instructor Feedback (Brittany)

## Specification Adherence

**50 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

## User Interface

**17 points**: The application is pleasant, logical, and easy to use. There no holes in functionality and the application stands on it own to be used by the instructor without guidance from the developer.

* Would have liked to have some visible user feedback when I enter an invalid URL. I see in the console you are logging `url is not valid`, but if I'm an average Joe user, I wouldn't think to look there to see what was going wrong.

## Data Persistence with SQL Database

**20 points**:  The application persists data in a SQL database with correct relationships between folders and URLs.


## Testing

**7 points**: Project has sporadic use of tests and multiple levels. Not all controller actions are tested. There are little or no attempts at integration testing.

* No client-side tests

* Server-side tests are really sparse, does not cover all happy and sad paths for each endpoint

* Should be using a database for your server-side tests to more closely mimic the development and production environments rather than `app.locals`. I know we showed you testing with `app.locals` in the lesson plan, but piecing together how to do it with a database without any hand-holding would have been a really good learning experience.

## JavaScript Style

**12 points**: Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.

* Generally it's best to start your [imports](https://github.com/Adamj1232/Jet-Fuel/blob/master/server.js#L1-L16) with any third-party libraries (lines 5-8), blank line, custom imports and configuration (lines 1-3), blank line, and then any app/server specific setup (lines 13-16, remove blank line on 15).

* [This](https://github.com/Adamj1232/Jet-Fuel/blob/master/server.js#L18) isn't being used.

* What happens if you rename your `index.html` [file](https://github.com/Adamj1232/Jet-Fuel/blob/master/server.js#L20-L22)? What kind of response would be given back here? Would be nice to put some error handling or a 404 in those cases.

* You are explicitly setting `link.name` on line [66](https://github.com/Adamj1232/Jet-Fuel/blob/master/server.js#L65-L72) and then using that to trigger an error handler if it does not exist on line 68. This error handler will never be called if you are explicitly setting that value just 2 lines earlier.

* Don't curse in your [error handling](https://github.com/Adamj1232/Jet-Fuel/blob/master/server.js#L88).

* Inconsistencies with sending back appropriate [status codes](https://github.com/Adamj1232/Jet-Fuel/blob/master/server.js#L103). Sometimes you're not sending them at all. When you perform a successful operation but don't send any data back, you should use a 204 instead of a [200](https://github.com/Adamj1232/Jet-Fuel/blob/master/server.js#L114).

* If [this](https://github.com/Adamj1232/Jet-Fuel/blob/master/public/links.js#L15-L26) is something you want to call immediately, you could write it as an IIFE instead of declaring it then calling it.

* Any reason we're using == [here](https://github.com/Adamj1232/Jet-Fuel/blob/master/public/links.js#L31) instead of ===? And [here](https://github.com/Adamj1232/Jet-Fuel/blob/master/public/links.js#L39)? And [here](https://github.com/Adamj1232/Jet-Fuel/blob/master/public/links.js#L91)? We should always be doing strict equals for equality comparisons.

* Instead of using `setAttribute` [here](https://github.com/Adamj1232/Jet-Fuel/blob/master/public/links.js#L50) you could use the `classList` property.

* If you're not going to use semi-colons anywhere in your codebase, be [consistent](https://github.com/Adamj1232/Jet-Fuel/blob/master/public/links.js#L115).

* Every promise you use should always have a [catch](https://github.com/Adamj1232/Jet-Fuel/blob/master/public/links.js#L120-L129) block. You know this.

* Always do your assignment on the left-hand side when using [ternaries](https://github.com/Adamj1232/Jet-Fuel/blob/master/public/helpers.js#L27-L30). This is really difficult to read and produces repeat code when you put the assignment on the right. e.g. this should be written:

```js
let fetchUrl = (deleteType === 'url') ?  `/api/v1/links/${id}` : `/api/v1/links/folder/${folderName}`;
```

* This looks like a [hack](https://github.com/Adamj1232/Jet-Fuel/blob/master/public/helpers.js#L40) of some sort.

* Stylistically, there are a lot of inconsistencies with spacing and formatting. It makes the entire codebase more difficult to read. I would suggest adding a linter and enforcing it to clean up the javascript across the board.

* [No](https://github.com/Adamj1232/Jet-Fuel/blob/master/public/helpers.js#L66-L68)

## Workflow

**12 points**: The developer makes a series of small, atomic commits that document the evolution of their application. There are some formatting issues in the code base and some commits are handling more than they should be.

* Commit messages are sometimes a bit too long which makes it difficult to read the history. [This blog post](https://chris.beams.io/posts/git-commit/) gives some good rules-of-thumb for writing appropriate commit messages.

* Commits often have irrelevant or unrelated changes in them that aren't described by the message. Changesets per commit should be smaller and more cohesive. Also [no committing console.logs](https://github.com/Adamj1232/Jet-Fuel/commit/ec3c755570dcfb5be5c76e1ce8a00b27be115632)



### To get a 3 on this project, you need to score 110 points or higher
### To get a 4 on this project, you need to score 135 points or higher

# Final Score: 118 / 150
