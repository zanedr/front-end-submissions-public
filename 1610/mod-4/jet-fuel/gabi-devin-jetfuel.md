Jet Fuel Submission Form
#Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)


#Basics

### Github Repository for the Project

[Repo](https://github.com/gprocell927/jetFuel)

### Deployed Application

[Deployed](https://jetfuelproject.herokuapp.com/)

### Commits in the Github Repository for the Project

[Commits for Project](https://github.com/gprocell927/jetFuel/commits/master)



# Completion

Were you able to complete the base functionality?

No - Our popularity and date created sort is WIP.

# Code Quality

#### Specific block of your code on Github that you are proud of

[Proud Code](https://github.com/gprocell927/jetFuel/blob/master/public/index.js#L55-L67)

We are proud of this piece of code because it delt with a weird issue with trailing commas between all our folders and links. We figured out the reason the commas existed was because the way we were appending to the page was mapping over the array and returning a single string. We figured out that using a reduce instead got rid of the commas.

#### Specific block of your code on Github that you are not proud of

[Not Proud Code](https://github.com/gprocell927/jetFuel/blob/master/server.js#L79-L89)

We don't feel awesome about this code because it is WIP. We worked for a long time and learned a lot about databases and interactions, but we weren't able to figure out the relations between our client side and database to implement the counter. 

#### Passing Tests
![Passing Tests](http://g.recordit.co/so23yGsPrg.gif)


#### Notes
This project was fun, terrible and magical. Why is it called JetFuel? We had fun working through problems... getting to build a database was cool, we feel smarter... but confused. It was hard. We want to finish the counter to feel good about ourselves. I think there's still a lot of confusion about how to form relationships between the client side and the server side/database.

#### Instructor Feedback

## Instructor Evaluation Points

The following set of points are distributed at the discretion of the instructor.

### Specification Adherence

* **40 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

All functionality was met except for the following:
* Can only sort in one direction (not both ASC and DESC for both date and popularity).

### User Interface

* **15 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

The application is easy to use and looks fairly decent. The improvement I would like to see is the URL table. The table could be better layed out with more space, the created date could be formatted better to be more human readable, and I would like to see the folder name above all the URL functionality.

### Data Persistence with SQL Database

* **20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

### Testing

* **15 points** - Project has a running test suite that tests and multiple levels but fails to cover some features. All controller actions are covered by tests. The application makes some use of integration testing.

Extensive endpoint tests, really liked to see that. No unit tests.

### JavaScript Style

* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

I liked the use of the helper functions in your client-side code to keep things cleaner. You should have pulled in all the functions at the bottom of the index.js file into the helper function (checkURL, sort...) and I would have liked to see all the DOM appending in it's own function (displayURLs).

### Workflow

* **20 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Lots of small commits and PRs. Good conversations.

## Projects are due on Friday 3/17, 12:00 p.m. We will provide a submission form for all teams to submit their repos.

## Project is worth 150 points with 15 extra points possible

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 135 points or higher

# Final Score: 125 / 150
