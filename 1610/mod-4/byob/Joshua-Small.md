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

- Points: x / 150
