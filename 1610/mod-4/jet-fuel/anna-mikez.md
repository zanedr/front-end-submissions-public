### Jet Fuel Submission form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)



# Basics

#### Github Repository
[JetFuel](https://github.com/apsitos/JetFuel)

#### link to Deployed
[JetFuels](https://jetfuels.herokuapp.com/)

#### Commits
[github commits](https://github.com/apsitos/JetFuel/commits/master)


#### Screeenshots
![jetfuel screen](http://i.imgur.com/5Gq86Xe.png)


## Completion

#### Were you able to complete base functionality?
* Not Quite

#### extensions
 N/A

# Code Quality
#### link to code you're proud of



#### code we are not proud of
[sadcodes](https://github.com/apsitos/JetFuel/blob/master/tests/server-test.js#L1-L54)

testing DB is hard


#### testing
![tests](http://i.imgur.com/12t6prE.png))
having trouble getting database set up in order to get endpoint tests to pass


### OTHER things
 Mike wants to shout out to Anna and Alex. Anna was very patient with me while I was/am struggling with wrapping my head around a lot of these concepts. she was this groups MVP. Thanks for being awesome Anna. Thanks to Alex for the early morning help and trying to help me understand these things.


# Instructors things

## Instructor Evaluation Points

The following set of points are distributed at the discretion of the instructor.

### Specification Adherence

* **40 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

All functionality was met except for the following:
* Can only sort in one direction (not both ASC and DESC for both date and popularity).

### User Interface

* **12 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

The application is easy to use and looks fairly decent. The improvements I would like to see is the URL table. The table could be better layed out with more space, the created date could be formatted better to be more human readable, and I would like to less white space.

The Folder list is also kind of a hot mess once it get's past 4 or 5 folders. It's hard to read the grey text on light blue background.

### Data Persistence with SQL Database

* **20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

### Testing

* **12 points** - Project has a running test suite that tests and multiple levels but fails to cover some features. All controller actions are covered by tests. The application makes some use of integration testing.

All endpoints are tested but only for happy path. No unit tests.

### JavaScript Style

* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

I really liked how you broke out your client-side code into really small, single responsiblity functions and had comments describing them. I would have liked to seen the DOM appending in it's own functions as well (displayUrls...). 

Server-side code looks good for the most part. I would delete those app.locals at the top so you don't get confused if you are using them or not. Also, NO CONSOLE.LOGS IN PRODUCTION CODE!! EVER!!!!

### Workflow

* **20 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Lots and lots and lots of commits and branches. Looking through the commits it looks like Anna did a majority of them, which is fine because Mike you indentified that and called it out.

## Projects are due on Friday 3/17, 12:00 p.m. We will provide a submission form for all teams to submit their repos.

## Project is worth 150 points with 15 extra points possible

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 135 points or higher

# Final Score: 119 / 150
