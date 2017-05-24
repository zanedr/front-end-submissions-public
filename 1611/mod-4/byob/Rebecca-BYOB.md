# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)
	
# Basics

#### Link to the Github Repository for the Project
[Your projects's repo URL](https://github.com/becs919/build-your-own-backend)
		
#### Link to the Deployed Application
[Your project's production URL](https://polish-data.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project
		
[Commits](https://github.com/becs919/build-your-own-backend/commits/master)
	
## Completion
		
#### Were you able to complete the base functionality?
	
* Seeded a database with at least 2 tables and 1 relationship?
	(Yes)
		
* Had at least 10 endpoints that returned responses with appropriate status codes?
	(Yes)
		
* Secured at least 4 endpoints with JWTs?
	(Yes)
	
* Enforced a linter and wrote code that conformed to it?
	(Yes) - but have a console.log for app is running on port 3000. 
		
* Wrote tests for both happy and sad paths for each endpoint?
	(Yes)
	
* Setup automatic deployments with CircleCI to a production app on Heroku?
	(Yes)
		
# Code Quality
	
#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo - Custom query](https://github.com/becs919/build-your-own-backend/blob/master/server.js#L63-L92)
[Link to code block in repo - README](https://github.com/becs919/build-your-own-backend/blob/master/README.md)

* Why were you proud of this piece of code?
		
I made a sweet README with all my endpoints and what they need in the body if they need a body. 
	
I am proud of my custom query because it was my first one I have made and it worked out pretty well. My custom query is for searching for a brand within all of the products. 
	
#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo - data](https://github.com/becs919/build-your-own-backend/blob/master/data/newPolishData.js#L1-L5)
[Link to code in repo - patch](https://github.com/becs919/build-your-own-backend/blob/master/server.js#L103-L132)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
	
I had to hard code my foreign keys after having trouble seeding the data with incrementing primary keys of brands. Robbie helped me a lot with this and figured out how to seed without hard coding but I didn't have time to implement that while getting everything else done that was needed for this project. 
		
For my patches, I am patching based on the param of the id and I didn't have enought time to check to see if the folder exists within the route. I would ideally like to check if the id exists, if so patch, if not send back error. Didn't have enough time to work on that. 
		
## Testing
		
Attach a screenshot or paste the output from your terminal of the result of your test-suite running

![Testing](http://g.recordit.co/nEg8emm28A.gif)
		
## Linting
	
Attach a screenshot or paste the output from your terminal of the result of your linter running

![eslint](http://g.recordit.co/kINo69Lg0p.gif)
	(console.log in app running on port 3000 in server.js)
	
#### Please feel free to ask any other questions or make any other statements below!
	
Working with the data was the hardest part of this project. It was tricky to manipulate the data to get it to seed properly. I spent about 3 days just working on that. 

## Instructor Evaluation Points (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Endpoints

* **60 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params.

### Data Persistence with SQL Database

* **40 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

* Be more descriptive with [migration names](https://github.com/becs919/build-your-own-backend/tree/master/db/migrations) so you can look at the names and get an idea of the evolution of your schema
* The indentation in [this file](https://github.com/becs919/build-your-own-backend/blob/master/db/migrations/20170517183444_maketables.js) is a little hard to read, not sure it's necessary -  did your linter tell you to do this?...
* Good job using the foreign key with the `nailPolish` [table](https://github.com/becs919/build-your-own-backend/blob/master/db/migrations/20170517183444_maketables.js) - typically, table names are lowercase
* Ideally, you wouldn't need to hard code the [foreign keys](https://github.com/becs919/build-your-own-backend/blob/master/data/newPolishData.js), but I get that this was tough

### Testing & Linting

* **25 points** - Project has a running test suite that covers most happy and sad paths for each endpoint. Linter has some errors that need fixing.

* Don't forget to test for response type like `html` or `json` (JSON in this case) - missing [here](https://github.com/becs919/build-your-own-backend/blob/master/test/routes.spec.js#L65) and other tests
* In [this case](https://github.com/becs919/build-your-own-backend/blob/master/test/routes.spec.js#L126), you are reaching [this error](https://github.com/becs919/build-your-own-backend/blob/master/server.js#L135) because the server is unable to parse the `:id`, which it expects to be an integer. What about the case where you pass in `823764` for the `:id`? This won't be in the database (at least for this project), and the database query will come back with an empty array, which 
* [Never](https://github.com/becs919/build-your-own-backend/blob/master/test/routes.spec.js#L166)
* [This](https://github.com/becs919/build-your-own-backend/blob/master/test/routes.spec.js#L341) is a great sad path case

### JavaScript Style

* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* [This](https://github.com/becs919/build-your-own-backend/blob/master/server.js#L145) is strange...you should be relying on auto-incrementing IDs and not generating random numbers yourself
* Some opportunity for refactoring [here](https://github.com/becs919/build-your-own-backend/blob/master/server.js#L164-L168) so there aren't a bunch of `else/ifs` - imagine if there were 10 columns in this table
* When you have a lot of routes in the server file, it's a good idea to break the routes out into other files know as `routers`. Take a look at the [Express documentation](https://expressjs.com/en/api.html#router) to see how they work.

To get a 3 on this project, you need to score 110 points or higher.

- Points: 140 / 150