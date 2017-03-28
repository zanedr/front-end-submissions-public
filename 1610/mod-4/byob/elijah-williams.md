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
[Your projects's repo URL](https://github.com/ejwill04/byob)

#### Link to the Deployed API
[Your project's production URL](https://build-your-own-backend.herokuapp.com/)

## Completion

#### Were you able to complete all 17 endpoints? If not how many did you complete?
* Yes

#### Were you able to complete all 34 endpoint tests? If not how many did you complete?
* Yes.  There are 38 tests.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/ejwill04/byob/blob/master/test/server-test.js#L405-L501)

* Why were you proud of this piece of code?

I'm testing a PUT endpoint in this bit of code.  The endpoint should only update what the user passes to the endpoint.  So, if a user passes all three params, it would update all of them.  If they don't pass any params, nothing gets updated.  

In order to check on what was updated, I first made GET requests, stored the repsonse in a local variable, and then compared the PUT response to these local variables.  

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/ejwill04/byob/blob/master/server.js#L36-L57)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

The nested IF statements aren't pretty, but they get the job done.  

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![Test Screenshot](http://i.imgur.com/QoMyQEz.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[Testing body params in PUT endpoint (as described in Proud code section)](https://github.com/ejwill04/byob/blob/master/test/server-test.js#L405-L501)

-----

#### JSON doc notes(http://jsonapi.org/format)!

[Link to section in docs](http://jsonapi.org/format/#crud-creating)
The docs specify that a POST request respond back with a 201.  The response should include a location in the header and a body that is structured as an object including Links to Self.  This seemed pretty verbose, so I provided a custom response based on what I thought was most applicable.  

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

-----

# Instructor Feedback

## Instructor Evaluation Points

The following set of points are distributed at the discretion of the instructor.

### Endpoints

* **60 points** - The application has all 17 endpoints (6 GETs, 3 POSTs, 3 PUTs/PATCHs, 3 DELETEs, 2 CUSTOM) with responses for happy and sad paths for each endpoint.

### Data Persistence with SQL Database

* **40 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

### Testing

* **30 points** - Project has a running test suite that has 34 passing tests (a sad path and a happy path test for each endpoint)

### JavaScript Style

* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.


Great job checking for the request.query before the database query. A lot of people were selecting everything then doing a filter based on the request.query. This is more performant.

```
app.get('/api/v1/companies', (request, response) => {
  if (request.query.state) {
    let state = request.query.state
    database('companies').where('state', state).select()
    .then(companies => {
      if (companies.length > 0) {
        response.status(200).json(companies)
      } else {
        response.status(404).json('State not found')
      }
    })
  } else {
    database('companies').select()
    .then(companies => {
      response.status(200).json(companies)
    })
    .catch(error => {
      console.error('error', error)
    })
  }
})
```

I'd like to see this be a little more specific around the responses. So check that the company object returned is Kentucky and has all the expected key/values. Right now this test does nothing to give me confidence that I return the right company.

```
  it('should query companies', (done) => {
    chai.request(app)
    .get('/api/v1/companies?state=KY')
    .end((err, res) => {
      if(err) { return done(err) }
      expect(res).to.have.status(200);
      expect(res).to.be.json;
      expect(res.body).to.be.a('array');
      expect(res.body).to.have.length(1);
      done()
    })
  })
```

Overall you did a great job on this project, well done!

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 140 points or higher

# Final Score: 145 / 150
