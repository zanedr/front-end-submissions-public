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
[Your projects's repo URL](https://github.com/jksmall0631/recipez-api)

#### Link to the Deployed API
[Your project's production URL](https://recipez-api.herokuapp.com/)

## Completion

#### Were you able to complete all 17 endpoints? If not how many did you complete?
* No - 15

#### Were you able to complete all 34 endpoint tests? If not how many did you complete?
* No - 30

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/jksmall0631/recipez-api/blob/master/server.js#L85)

* Why were you proud of this piece of code?
It took a bit to make connections between all of the tables

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/jksmall0631/recipez-api/blob/master/server.js#L37)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
I'm not sure this a useful endpoint.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
    GET /api/v1/users
      ✓ should return a list of users
      ✓ should return an error if the url does not exist
    GET /api/v1/recipes
      ✓ should return a list of recipes
    GET /api/v1/ingredients
      ✓ should return a list of ingredients
      ✓ should return an error if the url does not exist
    GET /api/v1/recipes_by_user/:user_id
      ✓ should return all recipes for single user
      ✓ should return an error if the ID does not exist
    GET /api/v1/ingredients_by_recipe/:recipe_id
      ✓ should return all ingredients for a specific recipe
      ✓ should return an error if the ID does not exist
    GET /api/v1/pantry_by_user/:user_id
      ✓ should return a users specific pantry ingredients
      ✓ should return an error if the ID does not exist
    POST /api/v1/users
      ✓ should create a new user
      ✓ should error out if no body is entered
    POST /api/v1/user_recipes/:user_id
      ✓ should add a new recipe
      ✓ should error out if no body or params are entered
    POST /api/v1/recipes_ingredients/:recipe_id
      ✓ should add a new ingredient
      ✓ should error out if no body or params are entered
    PATCH /api/v1/update_user/:user_id
      ✓ should update the users name
      ✓ should return 404 if incorrect path is entered
    PATCH /api/v1/update_pantry/:pantry_id
      ✓ should update the quantity in the pantry
      ✓ should return 404 if incorrect path is entered
    PATCH /api/v1/update_recipe/:recipe_ingredients_id
      ✓ should update the quantity in a recipe
      ✓ should return 404 if incorrect path is entered
    DELETE /api/v1/users/:user_id
      ✓ should delete a user
      ✓ should return 404 if incorrect path is entered
    DELETE /api/v1/recipes/:recipe_id
      ✓ should delete a recipe
      ✓ should return 404 if incorrect path is entered
    DELETE /api/v1/ingredients/:ingredient_id
      ✓ should delete an ingredient
      ✓ should return 404 if incorrect path is entered

  30 passing (4s)


#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

https://github.com/jksmall0631/recipez-api/blob/master/tests/server-test.js#L241



# Instructor Feedback

## Instructor Evaluation Points

The following set of points are distributed at the discretion of the instructor.

### Endpoints

* **50 points** - The application has all 17 endpoints (6 GETs, 3 POSTs, 3 PUTs/PATCHs, 3 DELETEs, 2 CUSTOM) with responses for happy and sad paths for each endpoint. 

Missing 2 custom endpoints but OK'ed by me due to data complexity

### Data Persistence with SQL Database

* **40 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

### Testing

* **10 points** - Project has a running test suite that has 34 passing tests (a sad path and a happy path test for each endpoint)

You use the same sad path tests for PUTs and DELETEs. You need to make them legit sad paths. For example, on a PUT you send incorrect data and the DB should return and error and you test for that error.

The DELETE sad path should test deleting a resource that doesn't exist.

```
it('should return 404 if incorrect path is entered', (done)=> {
  chai.request(app)
  .post('/api/v1/1')
  .end((error, res)=> {
    expect(res).to.have.status(404)
    done()
  })
})
```

### JavaScript Style

* **12 points** - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.

Be consistent with namespacing your API endpoints. This is good:

```
app.delete('/api/v1/users/:user_id', (req, res) => {
  const {user_id} = req.params;

  database('users').where('id', user_id).del()
  .then(response => {
    database('users').select()
    .then(response => {
      res.status(200).json(response)
    })
  })
  .catch(error => {
    res.sendStatus(404)
  })
})
```

While it might make more sense to you, this is not good:

```

// Should be '/api/v1/users/:user_id'
app.patch('/api/v1/update_user/:user_id', (req, res) => {
  const {user_id} = req.params;
  const {name} = req.body;
  const username = {name}

  database('users').where('id', user_id).update(username)
  .returning('*')
  .then(user => {
    res.status(200).json(user)
  })
  .catch(error => {
    res.sendStatus(404)
  })
})
```


This is also bad practice:

```
// Should be '/api/v1/recipes'
// You should pass the user_id in the request body instead of as a param

app.post('/api/v1/user_recipes/:user_id', (req, res) => {
  const {user_id} = req.params;
  const {info} = req.body;
  const recipe_info = {info};

  if(info && user_id){
    database('recipes').insert(recipe_info)
    .returning('id')
    .then(id => {
      const recipe_id = id[0]
      const users_recipe = {user_id, recipe_id}
      database('users_recipes').insert(users_recipe)
      .then(response => {
        database('users_recipes').select()
        .then(recipes => {
          res.status(200).json(recipes)
        })
      })
    })
  }else{
    res.sendStatus(422)
  }
})
```
## Projects are due on Friday 3/24, 1:00 p.m. We will provide a submission form for all teams to submit their repos.

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 140 points or higher

# UPDATED Final Score: 112 / 150
