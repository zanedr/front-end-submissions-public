# Build Your Own Backend Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

* Fork this repo, if you haven't already and check out a branch
* **Use this README as a template to create a file in this folder with your name as the title.**
* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

# Basics

#### Link to the Github Repository for the Project
[Your projects's repo URL](https://github.com/apsitos/HappyHourAPI)

#### Link to the Deployed API
[Your project's production URL](https://hhapi-ap.herokuapp.com/)

## Completion

#### Were you able to complete all 17 endpoints? If not how many did you complete?
* Yes

#### Were you able to complete all 34 endpoint tests? If not how many did you complete?
* Yes, there are 35 tests.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of

I really like my delete functions. [Link](https://github.com/apsitos/HappyHourAPI/blob/master/server.js#L84) to the first line of the delete function in my restuarant describe block.

* Why were you proud of this piece of code?
Figuring out how to properly go through each table and reset the foreign keys was a fun challenge. 


#### Link to a specific block of your code on Github that you feel not great about


* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?



#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![Test Screenshot](https://github.com/apsitos/HappyHourAPI/blob/master/Screen%20Shot%202017-03-31%20at%209.02.12%20AM.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

-----

#### Please feel free to ask any other questions or make any other statements below!

Four tests are currently skipped. Two have errors relating to foreign-key constraints, and two have syntax errors that do not catch when testing the happy paths, only when testing the unhappy. I've rewritten the code both in the server file and in the test file multiple times and can't find the error. At 11pm on Saturday, I decided enough was enough.

-----

# Instructor Feedback

## Instructor Evaluation Points

The following set of points are distributed at the discretion of the instructor.

### Endpoints

* **50 points** - The application has all 17 endpoints (6 GETs, 3 POSTs, 3 PUTs/PATCHs, 3 DELETEs, 2 CUSTOM) with responses for happy and sad paths for each endpoint. But the 2 custom points are both using param queries instead of one custom calculation and they both return the same information as the /:id endpoints. 

### Data Persistence with SQL Database

* **40 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

### Testing

* **30 points** - Project has a running test suite that has 34 passing tests (a sad path and a happy path test for each endpoint)

Great job on getting all the tests, just be careful that you are testing status codes on sad paths (not sure if you did tests on other branch and they aren't commented out there)

```
it('DELETE should return an error if the user does not exist', (done) => {
      chai.request(app)
      .delete('/api/v1/drinkers/43')
      .end((err, res) => {
        expect(err).to.throw
        // expect(err).to.have.status()
        done()
      });
    });
```

### JavaScript Style

* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

Really good job on writing clean code on all the endpoints. This is awesome to see and very easy to read:

```
app.post('/api/v1/restaurants', (request, response) => {
  const { name, address, phone } = request.body;
  const restaurant = { name, address, phone, created_at: new Date };

  database('restaurants').insert(restaurant)
  .then(() => {
    database('restaurants').select()
    .then((restaurants) => {
      response.status(200).json(restaurants)
    })
    .catch(error => {
      console.error('Could not add restaurant', error);
      response.status(422).send('Please ensure the restaurant has a name, address, and phone number')
    });
  });
});
``` 

Only a couple of instances where you don't destructure like most of your endpoints (this is pretty nitpicky):

```
const time = request.query.time
const user = request.query.user

// Should be this
const { time } = request.query
const { user } = request.query

database('happyhours').where('id', id).update({ drinks: drinks })

// Should be this
database('happyhours').where('id', id).update({ drinks })
```

## Projects are due on Friday 3/24, 1:00 p.m. We will provide a submission form for all teams to submit their repos.

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 140 points or higher

# UPDATED Final Score: 135 / 150
