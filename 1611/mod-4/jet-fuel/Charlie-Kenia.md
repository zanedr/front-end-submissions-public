# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

# Basics

#### Link to the Github Repository for the Project
[jetfuel](https://github.com/kfarias/jet-fuel)

#### Link to the Deployed Application
[heroku](https://jetfuel-app.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Kenia](https://github.com/kfarias/jet-fuel/commits?author=kfarias)

-[Charlie](https://github.com/kfarias/jet-fuel/commits?author=dunncl15)

#### Provide a Screenshot of your Application
![wireframe](http://i.imgur.com/4nKV3Bf.png)

## Completion

#### Were you able to complete the base functionality?
* Yes w/ the exception of sorting by date

#### Which extensions, if any, did you complete?

 N/A

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/kfarias/jet-fuel/blob/8d0babe18b4ac0039a68f00cb3a63c7238c23d2f/server.js#L63-L70)

* Why were you proud of this piece of code?

We struggled for awhile to figure out how to increment the visits to each URL along with redirecting to the original URL. It was particularly satisfying to get this piece of code working and get a small win using a new framework.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/kfarias/jet-fuel/blob/8d0babe18b4ac0039a68f00cb3a63c7238c23d2f/test/routes.spec.js#L14-L30)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

We had some trouble setting up our testing environment and once it was set up seeding the test database did not seem to be consistent. Folders and links were changing positions in the returned array causing a lot of issues with testing. Our assumption is something is off with our before and afterEach blocks.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[Tests](http://i.imgur.com/TcZP76T.png)

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

-----


# Instructor Feedback (Brittany)

## Specification Adherence

**45 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

* Minor Bug: If I type in a new URL `http://google.com`, the redirect is broken because it tries to bring you to `http//google.com`. We should have some URL format validation on the front-end that only allows users to type a URL in a particular format. (Better yet would be to support all the different ways people might type a url.) The placeholder text that shows `www.example.com` is somewhat useful in guiding people in the right direction for how to format their URL, but I'd like to see some solid validation here as well.

* Minor Missing Feature: Users should be able to sort URLs in ascending or descending order. I would expect to be able to double-click the sort buttons and have the sort order reversed, with some sort of visual indicator (up/down arrows?) telling me the current sort.

## User Interface

**18 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

* Looks nice! Easy to use and follow the interaction flow with this design.

* I'd like to see some visual indication of the 'submit' button being disabled if a user hasn't selected a folder or hasn't entered a URL. 

## Data Persistence with SQL Database

**20 points** - The application persists data in a SQL database with correct relationships between folders and URLs.

## Testing

**15 points** - Project has a running test suite that tests and multiple levels but fails to cover some features. All controller actions are covered by tests. The application makes some use of integration testing.

* You're correct in your assumption that one of your before/afterEach blocks is a bit off. In your [afterEach](https://github.com/kfarias/jet-fuel/blob/master/test/routes.spec.js#L26) block you are only doing a migration rollback, and you're not re-seeding the database. Although you're reseeding in `beforeEach`, the rollback is actually manipulating your schema rather than simply clearing out and re-seeding your data. I know the blog post we linked you all to showed the rollback call in the before and after hooks, but that could actually lead you astray if you're manipulating your schema during your tests like that. We will clarify this for future mods. In your [test seed data](https://github.com/kfarias/jet-fuel/blob/master/db/test/seeds/folder.js), you could also manually insert the `id` fields for folders & urls so that it doesn't auto-increment. This gives you slightly more control over exactly what's in your test database so that id values aren't changing around on you every time a seed runs.


## JavaScript Style

**15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* Wonderful job making sure to always include `.catch()` blocks when working with promises. One day we will do a lesson on more proper/useful error handling, but this is a good first step.

* You can and should still send along an appropriate status code for your [redirect](https://github.com/kfarias/jet-fuel/blob/master/server.js#L67).

* The URL endpoint [here](https://github.com/kfarias/jet-fuel/blob/master/server.js#L84-L94) is a little off. I know it still works, but you want to try to match up your POST request URLs with your GET request URLs. i.e. to get the links for a particular folder, you have an endpoint that's like [/api/v1/folders/:id/links](https://github.com/kfarias/jet-fuel/blob/master/server.js#L53). I would stay consistent with this format and use it for your POST request as well. Otherwise it's a little tricky to tell where exactly that new URL is getting POSTed to. It does not clearly demonstrate that any new URL is going to be POSTed under a specific folder.

* The functionality within your [document.ready](https://github.com/kfarias/jet-fuel/blob/master/public/app.js#L4) doesn't actually need to be wrapped in `document.ready`. A fetch request doesn't depend on the DOM existing, so you could actually kick off that GET request immediately. Only functions that are intended to be executed right away **and** depend on a DOM element should be wrapped in `document.ready`.

* Make sure you understand the convention of prefixing variables with the dollar sign as you've done [here](https://github.com/kfarias/jet-fuel/blob/master/public/app.js#L25-L26). Neither of these actually reference a jQuery element, which is when you'd want to prefix with a dollar sign. They both represent an ID attribute or an element value - not the elements themselves.


## Workflow

**15 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

* Nice, tiny commits and use of feature branches. Would be nice to see you file some github issues that coincide with all the branches you've made. (You can autoclose issues by putting the issue number in your Pull Requests/commit messages.) 

* Thanks for taking out those [console.logs](https://github.com/kfarias/jet-fuel/commit/474db0f7f61de3acfe334f3d15698534c39c8f8f)! Next week we'll go over some strategies that will prevent you from committing this type of code in the first place.

* I also tell everyone to make sure you have a consistent style for your commit messages. It is super nitpicky, but try to format them in the same manner as the default 'Merge' commits that github creates: 'Start with capital letter no punctuation'. You'll likely join dev teams that have a standard style for messages and they'll hound you for it until you conform. [Here](https://chris.beams.io/posts/git-commit/) is a blog post on some good conventions.


### To get a 3 on this project, you need to score 110 points or higher
### To get a 4 on this project, you need to score 135 points or higher

# Final Score: 128 / 150