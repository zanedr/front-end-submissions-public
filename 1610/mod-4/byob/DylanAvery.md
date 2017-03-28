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
[Your projects's repo URL](https://github.com/dylanavery720/byobackend)

#### Link to the Deployed API
[Your project's production URL](https://bringyourownbible.herokuapp.com/)

## Completion

#### Were you able to complete all 17 endpoints? If not how many did you complete?
* Yes

#### Were you able to complete all 34 endpoint tests? If not how many did you complete?
* Yes.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/dylanavery720/byobackend/blob/master/nightmare.js)

* Why were you proud of this piece of code?

At first I was scared it would be a foolish rabbit hole to have my scraper minify my text for me, but it was fairly easy and pretty cool.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/dylanavery720/byobackend/blob/master/knexfile.js)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

IDK I have no control over this config but I am having trouble migrating and seeding my production DB.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![Test Screenshot](http://imgur.com/a/s0syU)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[Testing a messed up search](https://github.com/dylanavery720/byobackend/blob/master/tests/server-test.js)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

Failing tests don't always fail, but their randomness indicates something is out of my control which I dont like. Also, having trouble seeding
the Production database, I am getting a "unable to aquire a connection" error. 

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

* **8 points** - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.


For your POSTING of users:

If you are incrementing the id in the database for users (which you are), don't send the id in the request. Let the DB create the id for you.

You'd never get to the second catch here, don't try to send back two different status codes on a DB error unless you are checking the specifics of the error and responding  with different status codes based on the error.

```
app.post('/api/v1/users', (req, res) => {
  const first_name = req.body.first_name
  const last_name = req.body.last_name
  const email = req.body.email
  const id = req.body.id || null
  const user = { id, first_name, last_name, email, created_at: new Date }
  database('users').insert(user)
        .then(() => {
          database('users').select()
          .then((users) => {
            res.status(200).json(users)
          })
        })
      .catch((error) => {
        res.status(404).send(error)
      })
      .catch((error) => {
        res.status(422).send(error, '422')
      })
});
```

Using destructuring for the req.body. You could have done this in a several places to remove a lot of lines of code.

```

app.put('/api/v1/users/:id', (req, res) => {
  const first_name = req.body.first_name
  const last_name = req.body.last_name
  const email = req.body.email
  
  // Instead do this:
  const { first_name, last_name, email } = req.body
```

Check for the search before the DB query. That way you can use a WHERE statement with the search instead of grabbing all artists and filtering by the search if it exists.

```
app.get('/api/v1/artists', (req, res) => {
  const search = req.query.search
  database('artists').select()
        .then((artists) => {
          if (search) {
            const searched = artists.filter((obj) => {
              if (obj.name === search) {
                return obj
              }
            })
            if (searched.length < 1) {
              res.status(404).send({ error: 'no match' })
            } else {
              res.status(200).json(searched)
            }
          }
          else {
            res.status(200).json(artists)
          }
        })
        .catch((error) => {
          res.status(404).send(error)
        })
});
```

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 140 points or higher

# Final Score: 138 / 150
