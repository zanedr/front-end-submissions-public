# Real Time Submission Form

[Project Spec](http://frontend.turing.io/projects/real-time.html)

------

# Basics

#### Link to the Github Repository for the Project
[Poehler](https://github.com/andrewLcrist/poehler)

#### Link to the Deployed Application
[Live Application](http://poehler.herokuapp.com/form)

#### Link to Your Commits in the Github Repository for the Project

-[Andrew](https://github.com/andrewLcrist/poehler/commits/master)

#### Provide a Screenshot of your Application
[Poehler Form Page](http://imgur.com/a/HXIPX)

## Completion

#### Were you able to complete the base functionality?
* Yes, however, when trying to persist user responses I created a new bug that is currently preventing me from being able to have basic functionality in my production site. I altered the databases and am unable to post or get currently. Oddly, I'm able to have full functionality on localhost. I think the error is due to a knex issue.

#### Which extensions, if any, did you complete?

None, only partial completion of the persistance of data.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
* Why were you proud of this piece of code?
[link](https://github.com/andrewLcrist/poehler/blob/master/public/poll.js#L115-124)

I was proud of this piece of code because it was a saving grace in terms of needing to go back through my tables, renaming them then subsequently updating all paths to that table. By adding the dynamic classname of 'nickname' I was able to selectively delete the user's previous answer selection.

*Update* Alex is awesome and two words cost me so much pain. Prod is now live. 'Heroku run' cost me more time than I want to admit and I feel defeated. I somehow managed to read over the most impotant thing in the doc I read over and over and over.Polls persist, but votes currently do not.

#### Link to a specific block of your code on Github that you feel not great about
* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
[link](https://github.com/andrewLcrist/poehler/blob/master/public/poll.js)

I'm not proud of my poll.js at all. I had originally broken out my auth.js but was not able to find a way to work around having separate files. Now I'm left with this gigantic page of code that is confusing and mixed.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[Tests](http://imgur.com/a/HXIPX)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

-----

#### Please feel free to ask any other questions or make any other statements below!

This project was incredibly hard. I thought it would be a good idea to pivot it from jet-fuel, for the sake of practicing a pivot and minimizing duplicative work. However, this proved to make me spend a lot more time upfront updating the code that I needed to go back and change nayway at the end of the project.

The dirt is in the details. The dirt is embarrassing, but I hope that the concepts that I missed early and late in this project will be remembered when learning new tools in the future.

-----
# Instructor Notes

Base Score: 104/150

Fix one of the UI or general bugs below to bump concept and feature score and receive full points.

## Concept and Features

40/50 - All planned features are delivered by major bugs and UI concerns need to be fixed asap.

Major Bug: All old polls are overwritten by the newest poll

UI Concern: `He gets back a link` - is a little questionable - while the link does get appended to the list of all polls, it's a little hard for the user to tell which poll is correct

UI Concern: User is able to vote without logging in - which results in a broken image link under that vote. User should be prompted to log in or a default image should be uploaded if they are not logged in when they vote

Bug: Once I logged in, I was unable to vote on the poll. I had to revisit the link in order to have my clicks be registered.

Major UI Concern: Actual website root directory gives a 404 Knope (which is an awesome error screen) - the root directory of the app should be the page that creates the forms.

UI Concern: If you only do 3 options, you get a blank 4th option

OMG sign out is literally the best.

## Code Quality

35 points - Developer solves problems with a balance between conciseness and clarity and often extracts logical components. Developer can speak to choices made in the code and knows what every line of code is doing.

[Nice!](https://github.com/andrewLcrist/poehler/blob/master/server.js#L52-L56)

[This fragile structure](https://github.com/andrewLcrist/poehler/blob/master/server.js#L69-L74) is something I would strongly consider you move away from on future projects. I think you made the right call in not trying to overhaul this in favor of making sure your bugs were handled - but now that you've lived with it for a while, I would try to either document it in your code base or fix it.

[Good start on splitting out logic in this helpers file](https://github.com/andrewLcrist/poehler/blob/master/helpers.js). You want to be careful not to create a junk drawer by calling a file helpers. Really, everything in this file is actually your database queries for a poll. It's an ORM. So name this file as such!

[Too many arguments per function](https://github.com/andrewLcrist/poehler/blob/master/helpers.js#L7) here - in part because of the fragile structure of how you keep track of options - too many arguments to one function is usually a good indicator of a code smell.

[A lot of code formatting issues in here](https://github.com/andrewLcrist/poehler/blob/master/public/auth.js)

Over all you have a really good start at refactoring this project. It looks better than a lot of other code that I've reviewed and you clearly put effort into this. There's still work to do, as seen above, but really solid effort.

## Testing

12 points - The application has a small number of routes tested and no unit tests. No tests are failing on master.

## Workflow

No PRs! 

17 points - The developer makes a series of small, atomic commits that document the evolution of their application. There are no formatting issues in the code base.
