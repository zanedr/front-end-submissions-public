## BYOB EDM-DB

[GitHub repo-checkout staging branch](https://github.com/juliankyer/db-edm)

[Heroku](https://db-edm.herokuapp.com/)

[Commits](https://github.com/juliankyer/db-edm/commits/master)
Note: I started this project over yesterday afternoon after unsuccessfully trying to fix my original. 

### Completion
##### Seeded a database with at least 2 tables and 1 relationship? 
Yes

##### Had at least 10 endpoints that returned responses with appropriate status codes? 
Yes 

##### Secured at least 4 endpoints with JWTs?
Yes

##### Enforced a linter and wrote code that conformed to it?
Yes

##### Wrote tests for both happy and sad paths for each endpoint? 
Yes

##### Setup automatic deployments with CircleCI to a production app on Heroku? 
Yes

### Code Quality
I like [this](https://github.com/juliankyer/db-edm/blob/f01be61d33bcbafbad13f7d51422b5ba5c50eb24/server.js#L129-L141) chunk of code because I learned a lot in terms of figuring out how to handle errors and do some basic authorization checks. The if/else also caused some linter errors and I liked having to dig into that to figure out why.

I'm not crazy about [this](https://github.com/juliankyer/db-edm/blob/f01be61d33bcbafbad13f7d51422b5ba5c50eb24/server.js#L37-L54) chunk of code because it is from a lesson, so it wasn't something I wrote or struggled with, it was something I implemented. But I really like what it allows me to do in my project.



### Linter and Testing
[Linter and Test results](http://imgur.com/FpF4PNW)

...looks like if you don't have linter errors in eslint, there's no "congratulations, you have no errors" message. Which is BS.



-----

# Instructor Feedback [Brittany]

## Feature Completion

### Endpoints
**60 points**: Developer has implemented 11 of 10 endpoints and secured 4 of them with JWTs or have a custom endpoint based on query params.

* Great job with accurate error handling and proper response codes

### Data Persistence with SQL Database
**40 points**: The application contains at least 2 tables with a proper relationship between data sources.

* Seed files are a little intense with data. I would break out the actual json data into a separate file and import it into your seeds file so you can insert it all at once and keep the seed file clean and readable.

## Testing and Linting

**20 points**: Project has a running test suite that covers most happy and sad paths for the appropriate endpoints. The project has a linting configuration that passes with no errors.

### JavaScript Style
**15 points**: Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.

## Points: 135 / 150

