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
[BYOB](https://github.com/gprocell927/BYOB)

#### Link to the Deployed API
[Producción](https://byob-anesthesia.herokuapp.com)

## Completion

#### Were you able to complete all 17 endpoints? If not how many did you complete?
* Yes

#### Were you able to complete all 34 endpoint tests? If not how many did you complete?
* No. There are 24 tests.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[El código](https://github.com/gprocell927/BYOB/blob/master/server.js#L25-L49)

* Why were you proud of this piece of code?

I struggled with building the query/param endpoint. Initially I tried to make it it's own endpoint. Then I realized that making multiple requests to the same endpoint was not making for a fun time. Although the nested if statements bother me, I felt that this piece was easy enough to follow.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/gprocell927/BYOB/blob/master/test/server_test.js#L257-L330)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

I had trouble debugging errors involving my database and testing. Tests would pass until a certain unknown point, and then they would begin to fail. Most of the errors revolved around my before and after hooks. I would try to rollback and migrate my databases periodically,but that only got me so far. 

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![Testing GIF](http://g.recordit.co/XvLZX7QKBT.gif)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[Testing that a post request returns a 422 error if provided insufficient info -- does not pass)](https://github.com/gprocell927/BYOB/blob/master/test/server_test.js#L320-L342)

-----

#### Please feel free to ask any other questions or make any other statements below!
I am slowly starting to understand how to pick through more of the layers in referencing items that are linked between tables. 

I do still have some issues with test seed data. Theoretically, I don't feel that I should have had to stub data like I did for my tests. The tests also seemed to make sense to me, and I'm at a loss as to why they are not passing or why they pass intermittently. In conclusion, I don't fully grasp the connection of the seed data in before and after hooks within describe blocks. Shouldn't it be following the methods that were run on it? Ideally, each test within the block should have started with a fresh database, right?

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

* **10 points** - Project has a running test suite that has 34 passing tests (a sad path and a happy path test for each endpoint)
* 23 total tests, but extensive testing around data. 

### JavaScript Style

* **12 points** - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.


In your endpoints that have request queries (const species = req.query.species, be sure to check for species before the database query. That way if species exists, you can use a WHERE statement instead of selecting all and then filtering through the results:

```
app.get('/api/v1/patients', (req, res) => {
  const species = req.query.species

  database('patients').select()
  .then(patients => {
    if(species){
      const matchingPatients = patients.filter(patient => {
        return patient.species == species
      })
      if(matchingPatients.length === 0){
        res.status(404).send({
          error:'There are no existing patients belonging to that species.'
        })
      } else {
        res.status(200).send(matchingPatients)
        }
      }
      else {
        res.status(200).json(patients)
    }
  })
  .catch((error) => {
    res.status(404)
  })
})
```

I think you did a really good job with this project and produced a lot of consistent, clean API endpoints. You also had the most complex dataset of all the projects I reviewed so that was awesome to see.

Whenever you want to go over seeding test data, let me know and I can walk through the errors with you. It's hard to know the issues just looking at your repo but I'll definitely debug with you. Even though you didn't have all the tests/passing tests, I was really happy to see all the data validations in the tests you did have.


## Projects are due on Friday 3/24, 1:00 p.m. We will provide a submission form for all teams to submit their repos.

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 140 points or higher

# Final Score: 122 / 150
