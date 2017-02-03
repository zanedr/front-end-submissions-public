# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)


------

# Basics

#### Link to the Github Repository for the Project
[Your Repo](https://github.com/rcwestlake/jet-fuel)

#### Link to the Deployed Application
[Your Application](https://irwin-urls.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Ryan Westlake](https://github.com/rcwestlake/jet-fuel/commits?author=rcwestlake)

-[Alex Pilewski](https://github.com/rcwestlake/jet-fuel/commits?author=Pilewski)

#### Provide a Screenshot of your Application
![irw.in](http://g.recordit.co/q1RHtwXIFh.gif)

## Completion

#### Were you able to complete the base functionality?
* We have all the functionality except for rerouting when they paste the URL in the browser. It reroutes when they click on the shorted URL correctly, however. If was an issue with switching to the database and we can finish it this weekend if it impacts our score.

#### Which extensions, if any, did you complete?

- Per Extension:
  - Show an error with there is no data at the route
  - ![issue](http://g.recordit.co/qxpVblqNrM.gif)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
- Ryan [is proud of code](https://github.com/rcwestlake/jet-fuel/blob/master/db/migrations/20170126151836_add-folders-urls-tables.js#L1-L26)
- Alex [is proud of React ingenuity](https://github.com/rcwestlake/jet-fuel/blob/master/src/components/URL.js#L6-L36)

#### Link to a specific block of your code on Github that you feel not great about
* [Least proud of how we managed state in the App component](https://github.com/rcwestlake/jet-fuel/blob/master/src/App.js#L12-L18)

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
* [2 passing tests, 6 are skipped. We ran into issues when transitioning to the database](http://g.recordit.co/IlKKKr15jr.gif)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

-----

#### Please feel free to ask any other questions or make any other statements below!
Cheers! Also, we named our app Irwin, simply because it's a great name.

-----

# Instructor Feedback

From Alex & Meeka

- Points: (base 150)

124/150 - strong 3

## Base Expectations

**45/50**

This has the most usable functionality that we've seen - the following issues are noted

1. Cannot enter url in url bar and be redirected (can only do so from the UI because it's hard href'n) - [suspect issue is here](https://github.com/rcwestlake/jet-fuel/blob/master/src/server.js#L135-L145)
2. Cannot view links if we enter more than 3 links - can't scroll below the fold - See issue in this gif: http://g.recordit.co/frcuWdBvkw.gif
3. Sort only works if you are at all URLs, not in a specific folder - and sort is a little pointless given the scroll issue above.
3. Questionable extension since node kiiiind of does this for you. If you have a nice UI, or any kind of client side messaging, we would have given points for.

### User Interface

**7 points** - The application shows effort in the interface, but the result is not effective. The evaluator has some difficulty using the application when reviewing the features in the user stories.

This is the best looking or laid out application, but there are some serious downfalls that could have been easily fixed. If you fix them, we can bump this score and it would be a 4, pretty much.

Biggest issue is the inability to scroll, which made it impossible to eval on production after a certain point.

Second biggest is sort inconsistency, as mentioned above.

Other more nitpicky things:

Client side check for adding urls is cool - won't allow you to add a crappy URL most of the time! However - if you add `http://www.cnn.com` that can still be added and will not redirect correctly.

You can add blank folders with no names

Keep an eye on consistency with fonts. Remove UI elements that are not needed (like arrow beside the the folder header).

UI bugs are actually sometimes easier to detect because the app is prettier, if that makes sense. 

## Data Persistence with SQL Database

**20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

## Testing

**15 points** - Project has a running test suite that tests and multiple levels but fails to cover some features. All controller actions are covered by tests. The application makes some use of integration testing.

If you do end up revisiting and getting testing working, then we'll bump this up. Appreciate the skipping and notes to indicate what is going on!

Even though tests are skipped, there are good things going on

You are actually testing in these server tests that data and params are expected. 

Please add sad path tests in the future, make sure you have documented what happens when something doesn't work - especially since you put that as an extension ;)

## JavaScript Style

**17 points** - This is a strong 17. Cleanest code we've seen so far today.


1. [url naming convention is a little funky here](https://github.com/rcwestlake/jet-fuel/blob/master/src/server.js#L101) - the more semantic endpoint would be that folder endpoint returns all URL for that folder within the folder payload

```
{
  folder_name: 'cats',
  id: 1,
  urls: [
    {id: 1, name: 'cat.com'},
    // etc etc...
  ]
}
```

They still represent different tables - but this is just more in line with what you'll see in standard apis.

For example, [this code](https://github.com/rcwestlake/jet-fuel/blob/master/src/server.js#L135) might be better written

`/folders/:id/urls/:urlKey`

pattern is plural or word, param as a unique identifier, and repeat

[YESSSS!](https://github.com/rcwestlake/jet-fuel/blob/master/src/App.js#L85-L94) - this is very clear, very clear. Our nitpick would be that you probably want this type of function to live in a helper file that gets pulled in - but you are absolutely on the right track with length and naming.

Small nitpicks, `Container.js` is a vague name. In the return, you have a large JSX with a lot of ternaries going on - those should be their own separate functions. For example, [this block](https://github.com/rcwestlake/jet-fuel/blob/master/src/components/Container.js#L43-L51) should be its own function.

We love Folder.js, URL.js - checking prop types - super small components that make sense. Alex approves of your React code.

The `server-helpers.js` file is on the right path - but think about being a little more specific with naming and not creating a junk drawer. Especially since this file only has one thing in it. A helpers folder is appropriate, with named function files.

Great job on consistent code style and using consistent technology choices across the project.

## Workflow

**20 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Really love the commit messages, very clear what you did, lots of comments - no issues in the code that indicate a breakdown in workflow. Excellent work!
