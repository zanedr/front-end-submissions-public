# Build Your Own Backend Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

# Basics

#### Link to the Github Repository for the Project
[byob](https://github.com/StephanieEA/byob)

#### Link to the Deployed API
[fatal-police-shootings](https://fatal-police-shootings.herokuapp.com/)

## Completion

#### Were you able to complete all 17 endpoints? If not how many did you complete?
* Yes (I met the alternative solution I proposed to better analyze my data.)

#### Were you able to complete all 34 endpoint tests? If not how many did you complete?
* Yes

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/StephanieEA/byob/blob/5baa4fdf06180d334573c0af5984f8539024a722/helpers/helpers.js#L1-L19)

* Why were you proud of this piece of code?

I am proud of this code because I broke it into a separate helpers file (and I have been unsure about identifying helper functions in the past) and used reduce to get ratios (It's not complicated but math is not my favorite).  

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/StephanieEA/byob/blob/5baa4fdf06180d334573c0af5984f8539024a722/server.js#L188-L198)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

There are so many parts of the request body it almost doesn't make sense to destructure them but it does at the same time.  I didn't really try to refactor it because I think this is how it's supposed to be?  But it is ugly...

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

API Routes
    GET /api/v1/all
      ✓ should return all incident data for a request without any queries
      ✓ should return status 200 and the appropriate data for a query by state that exists
      ✓ should return a status 404 and the appropriate message for a query by state when none exists
      ✓ should return a status 404 and the appropriate message when the query by state is innacurate
    GET /api/v1/all/:id
      ✓ should return a 200 response and the specific incident for a correct id
      ✓ should return a response 404 and the appropriate message for a nonexisting id
      ✓ should return response 500, somethings wrong with db when the request param isn't an integer type
    GET /api/v1/state-territory
      ✓ should return a response 200 and all states and territories
    GET /api/v1/state-territory/:id
      ✓ should return a response 200 and a specific states or territory for a state/territory that exists
      ✓ should return  a response 404 and the appropriate message for a nonexisting id
      ✓ should return response 500, somethings wrong with db when the request param isn't an integer type
    GET /api/v1/state-territory/:abbreviation/incidents
      ✓ should return a response 200 and all incidents that occured in a specific state if they exist
      ✓ should return a response 404 and the appropriate message if there are no incidents for the state
    GET /api/v1/state-territory/:abbreviation/average
      ✓ should return a response 200 and the average age of victims from a given state/territory
      ✓ should return a response 404 and the appropriate error message when there are no victims from that state
    GET /api/v1/all/mental-illness
      ✓ should return a response 200 and the national ratio for incidents in which mental illness was clearly a factor
    GET /api/v1/all/body-camera
      ✓ should return a response 200 and the national ratio for incidents in which there is body camera footage
    GET /api/v1/armed
      ✓ should return a response 200 and the national ratios for the armed status of victims
    GET /api/v1/race
      ✓ should return a response 200 and the national ratios for the race of victims
    POST /api/v1/all
      ✓ should return a response 400 and all incidents with the added incident for a properly formatted request
      ✓ should return a status 422 and error message if the request does not include all properties
      ✓ should return a status 422 and error message of incorrect format if the request body includes unexpected values
    POST /api/v1/state-territory
      ✓ should return a response 200 and all states belonging to the specifed folder, including the added state
      ✓ should return a status 422 and error message of all properties are not provided if all properties aren't provided
      ✓ should return a status 422 and error message of incorrect format if the request body includes values other than name and abbreviation
    PATCH /api/v1/all/:id
      ✓ should return a response 200 and the updated incident for proper ids
      ✓ should return a response 404 and the appropriate error message for nonexisting ids
    PATCH /api/v1/state-territory/:id
      ✓ should return a response 200 and the updated incident for proper ids
      ✓ should return a response 404 and the appropriate error message for nonexisting ids
    DELETE /api/v1/all/:id
      ✓ should return a response 200 and delete a specific incident
      ✓ should respond with a 404, message of id not found, if the incident does not exist
    DELETE /api/v1/state-territory/:id
      ✓ should respond with a 200 status and delete a specific state or territory
      ✓ should respond with a 404, message of id not found, if the state does not exist

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[one sad path](https://github.com/StephanieEA/byob/blob/5baa4fdf06180d334573c0af5984f8539024a722/test/server-test.js#L164-L174)

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

-----

# Instructor Feedback

- Points: x / 150
