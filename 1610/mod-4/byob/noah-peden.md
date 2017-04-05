## Your projects's repo URL
[BYOB repo](https://github.com/noahpeden/byob)

## Link to the Deployed API
[Heroku link](https://np-byob.herokuapp.com)

## Completion

### Were you able to complete all 17 endpoints? If not how many did you complete?
I completed 15 endpoints, I'd like to make two endpoints targeting tuition fees and maybe languages? Or how many universities are in a specific ountry.

### Were you able to complete all 31 endpoint tests?

No I have 15 passing tests, but they do test sad paths and most of my core functionality.

### Code Quality

### Link to code block in repo
[Link to code block](https://github.com/noahpeden/byob/blob/master/db/migrations/20170322080045_initial.js)
### Why were you proud of this piece of code?
Reason you are proud of code

I'm proud of this because one of the biggest delays for me was migrating my data from a tsv and getting all the tables into one migration file was a big step.

### Link to a specific block of your code on Github that you feel not great about

[Link to bad code](https://github.com/noahpeden/byob/blob/master/server.js#L77)

### Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
Reason you don't feel awesome about this code.

It took me way too long to figure out that endpoints needed to be specific and that my freakin data was capitalized.

### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
![](http://imgur.com/a/P0Oqt)

Instructor Feedback

## Instructor Evaluation Points

The following set of points are distributed at the discretion of the instructor.

### Endpoints

* **50 points** - The application has 16 endpoints (6 GETs, 3 POSTs, 3 PUTs/PATCHs, 3 DELETEs, 1 CUSTOM) with responses for happy and sad paths for each endpoint.
* Missing one custom endpoint

### Data Persistence with SQL Database

* **40 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

### Testing

* **20 points** - Project has a running test suite that has 31 passing tests (a sad path and a happy path test for each endpoint)

Couldn't get DELETE sad paths passing


### JavaScript Style

* **15 points** - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.


## Areas of Improvement:

FIXED - Make sure to use proper api namespacing. You don't need the ending university in the endpoint (should just be /api/v1/university/:name).
Also, you should use a unique identifier (usually id) to find/update/delete a specific resource. There might be a case where there are multiple universities with the same name.

```
app.delete('/api/v1/university/:name/university', (request, response) => {
  database('university').where('name', request.params.name).del()
      .then(() => {
        database('university').select()
        .then((university) => {
          response.status(200).json(university)
        })
      })
      .catch((error) => {
        response.status(404).send(error)
      })
});
```

BE AWARE - Be consistent in your spacing:

```
app.get('/api/v1/university', (request, response) => {
  database('university').select()
  .then((university)=> {
    response.status(200).json(university);
  })
  .catch(function(error) {
  console.error('somethings wrong with db')
  console.log(error)
  response.status(404)
  });
})

app.get('/api/v1/university/:id', (request, response) => {
  database('university').where('country_id', request.params.id).select()

  .then(function(university) {
          if (university.length < 1) {
            res.status(404).send({ error: 'university does not exist' })
          }
            response.status(200).json(university);
          })
          .catch(function(error) {
            console.error('somethings wrong with redirect')
          });
})
```

FIXED - Take advantage of destructuring:

```
// Instead of this:
  const id = request.body.id
  const name = request.body.name
  const tuition_fee = request.body.tuition_fee
  const language = request.body.language
  const link = request.body.link
  const country_id = request.body.country_id

// Do this:
	const { id, name, tuition_fee, language, link, country_id } = request.body
```

FIXED - Be aware of when you are catching errors. Would it ever send the 422 status code?

```
  database('university').update(university)
        .then(() => {
          database('university').select()
          .then((university) => {
            response.status(200).json(university)
          })
        })
      .catch((error) => {
        response.status(404).send(error)
      })
      .catch((error) => {
        response.status(422).send(error, '422')
      })
```

WRITE MORE TESTS! Even if you think you've tested the 'meat of your app', on the job if someone runs into an edge case that you haven't thought of, they are going to be very upset that shit doesn't work and odds are lots of other people will run into the same error. Don't assume because 90% of your code is tested that the other 10% is good.



## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 140 points or higher


# UPDATED Final Score: 125 / 150
