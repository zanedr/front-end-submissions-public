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
[gitHub](https://github.com/jwood11atx/Jet-Fuel)

#### Link to the Deployed Application
[jetfuelmelts!](https://jetfuelmelts.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[justin wood](https://github.com/jwood11atx/Jet-Fuel/graphs/contributors)

-[justin wood](https://github.com/jwood11atx/Jet-Fuel/commits/master)

#### Provide a Screenshot of your Application

![](http://i.imgur.com/GJCN6ui.png)


## Completion

#### Were you able to complete the base functionality?
* Yes

#### Which extensions, if any, did you complete?

- Reverse sort?

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/jwood11atx/Jet-Fuel/blob/master/app/helpers/api.js)

* I guess I'm most proud of actually taking the time to refactor my code. I did 3 sessions of refactoring and tried to break things up as much as possible. Also I feel this is the best I have organized my code. I'm actually equally proud of my tests. I finally got to spend a chunk of time testing.


#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo]https://github.com/jwood11atx/Jet-Fuel/blob/master/app/index.html)

* I didn't spend much time with the html code. I kinda just built it out without really thinking about it too much. I just knew what kind of sections and containers I needed and never revisited it to clean up.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![](http://i.imgur.com/pTWZiWu.png)

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

* Really enjoyed the project! Looking forward to learn more backend and also I have a commented out test I'd like to get help with. It's a PATCH request that would never actually change the data in the test database.

-----

# Instructor Feedback - Brittany

## Specification Adherence

* 50 points: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

(Reverse sort was not an extension based on the outline [here](http://frontend.turing.io/projects/jet-fuel.html))


## User Interface
* 17 points - The application is pleasant, logical, and easy to use. There no holes in functionality and the application stands on it own to be used by the instructor without guidance from the developer.

Nice super hero colors. One tiny nitpick is it might be nice to see the timestamp for the URLs (if they're created on the same date, it's not easy to tell that the sorting is accurate.)

## Data Persistence with SQL Database

* 20 points - The application persists data in a SQL database but with correct relationships between folders and URLs.

## Testing

* 15 points - Project has a running test suite that tests and multiple levels but fails to cover some features. All controller actions are covered by tests. The application makes some use of integration testing.


## JavaScript Style

* 15 points - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

Functions are nice and modular, easy to read. I dig em. Just make sure you are always catching any Promise errors when using fetch. I'd like to see `.catch()` blocks after all your `.thens()`. (Like [here](https://github.com/jwood11atx/Jet-Fuel/blob/master/app/helpers/api.js#L17)). Another common convention when working with a particular API is to extract the 'root' of the URL into a variable. In your case it would look something like:

```javascript
const API_ROOT = `http://localhost:3000`;

fetch(`${API_ROOT}/folders/${folderId}/`, {
  method: 'GET'
})
```

This pattern makes it easy to toggle between different environments (e.g. you might be using localhost:3000/api/ for development, http://jetfuel.staging.com/api/ for a staging server and http://jetfuel.com/api/ for production). Or even if your local port changes, you would only have to update that base root URL in one place rather than in every fetch request.

When doing a `POST` to [create a new record](https://github.com/jwood11atx/Jet-Fuel/blob/master/server.js#L35), the status code should be 201 rather than 200 if things were successful. Take a look at all the status codes that exist [here](http://www.restapitutorial.com/httpstatuscodes.html).

I'm actually surprised that [new Date](https://github.com/jwood11atx/Jet-Fuel/blob/master/server.js#L30) works without the [parens](https://github.com/jwood11atx/Jet-Fuel/blob/master/server.js#L63).

Is this [finally](https://github.com/jwood11atx/Jet-Fuel/blob/master/server.js#L79) doing anything in particular? 

Better names for the [viewSort](https://github.com/jwood11atx/Jet-Fuel/blob/master/app/main.js#L9) would be ascending/descending (or asc/desc) rather than up/down. Up/down is a more...geographical? descriptor rather than an ordering descriptor.

I know we see a ton of examples out there just using words like `json` or `payload` for data variables but let's be more descriptive/informative [here](https://github.com/jwood11atx/Jet-Fuel/blob/master/app/main.js#L13-L14). I would rename that json argument to `folders`, or `foldersJSON`.

## Workflow

* 20 points - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Make sure your .gitignore file includes `.DS_Store`. That's a hidden file created on OSX when you use the Finder application and we don't want that committed to our repos.

Commits are otherwise nice and tiny, the diffs are readable and relevant to their commit messages. Good work!

Points: 137 / 150
