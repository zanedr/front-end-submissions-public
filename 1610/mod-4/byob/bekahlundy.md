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
[Dog Extension](https://github.com/bekahlundy/dog-api-extension)

#### Link to the Deployed API
[Heroku](https://pup-pals-db.herokuapp.com/api/photos)

## Completion

#### Were you able to complete all 17 endpoints? If not how many did you complete?
* Yes

#### Were you able to complete all 34 endpoint tests? If not how many did you complete?
* Yes

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[this get request](https://github.com/bekahlundy/dog-api-extension/blob/master/server.js#L28)

* Why were you proud of this piece of code?
I spent a long time going over this with meeka, and I am happy with how it turned out. It was difficult to figure out at first but i feel more comfortable with it now

#### Link to a specific block of your code on Github that you feel not great about
[this get request](https://github.com/bekahlundy/dog-api-extension/blob/master/server.js#L110)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

I am not sure about this get request. I think I should have had another get request like the one above, where i can get every photo associated with one feeling, instead of just one photo

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![passing-tests-screenshot](http://i.imgur.com/XHx87tx.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[unhappy path](https://github.com/bekahlundy/dog-api-extension/blob/master/test/server-test.js#L230)
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

Great job on this project, you put in a lot of time and effort and it showed. There were just a couple of little things for improvment. In this GET request, you can use the photoId to grab the feeling with that photoId, however since you are reusing the same feeling for multiple photos (happy associated with a lot of photos), I would have included a feeling_id for each photo. So basically reverse the relationship. 

Also, in the sad path, the response.status(404).json(feeling) won't work because it doesn't know what feeling is:

```
app.get('/api/feelings/:photoId', (request, response) => {
  database('feelings').where('photoId', request.params.photoId).select()
  .then((feeling) => {
    response.status(200).json(feeling)
  })
  .catch((error) => {
    console.log(error)
    response.status(404).json(feeling);
  })
})
```

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 140 points or higher

# Final Score: 145 / 150
