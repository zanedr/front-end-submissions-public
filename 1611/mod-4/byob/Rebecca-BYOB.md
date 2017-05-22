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
* **40 points** - Developer has implemented all 10 endpoints but did not secure 4 of them with JWTs or have a custom endpoint based on query params.
* **20 points** - Developer is missing endpoints and has not secured or customized any of the ones that have been implemented.

### Data Persistence with SQL Database

* **40 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.
* **20 points** - The application persists data in a SQL database but with some incorrect relationships between folders and URLs.
* **0 points** - The application does not persist data in a SQL database.

### Testing & Linting

* **30 points** - Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. The project has a linting configuration that passes with no errors.
* **20 points** - Project has a running test suite that covers most happy and sad paths for each endpoint. Linter has some errors that need fixing.
* **10 points** - Project has significant lack of testing for happy and sad paths of endpoints; Linter is failing on multiple lines.

### JavaScript Style

* **20 points** - Application has exceptionally well-factored code with little or no duplication and all components separated out into logical components. There _zero_ instances where an instructor would recommend taking a different approach.
* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.
* **12 points** - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.
* **5 points** - Your application has a significant amount of duplication and one or more major bugs. Developer cannot speak to most choices and does not know what every line of code is doing.

- Points: x / 150