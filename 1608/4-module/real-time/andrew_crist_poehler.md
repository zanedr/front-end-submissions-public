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

# Instructor Feedback

- Points: (base 150)
