## Students:
## Evaluator:
## Notes:

**MOVIE SPEC**:

```
Iteration 0:
* Pull in movie API
* Pull most recent movies from MovieDB API.
* Display each movie on root index /

Iteration 1:
* Sign In / Sign Out Functionality
* Be able to sign in on page /login and redirect user to /
* Flash "Email and Password do not match" - if password is incorrect
* Ability to create a user.
* Flash "Email has already been used" - if email has been taken
* Should only take legit emails - regex - Extension

Iteration 2: Favorites
* Each movie should be displayed with a favorite button.
* If the user is not signed in and clicks on a favorite button the user will be prompted with the request to create an account.
* Validate favorites before adding to db. Aka does that user already have the movie stored as favorites.
* If the user visits /favorites they should see a list of all their favorite movies.
* Once on /favorites the user should have the option to delete the movie.
```

### Specification Adherence  

<!-- * 3: The application consists of one page with all of the major functionality being provided by React. No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use. -->
* 2.5: The application is in a usable state, but is missing 1 or more of the features outlined in the specification above.

### Redux Architecture

* 3: At least one component is not connected with Redux appropriately. Application state is mutated by more than just Redux. The Redux store is missing application data that it should be handling.

### Routing

* 3: Application is a single page and uses the React Router but does not display the appropriate components upon navigating.


### JavaScript Style

* 3: Application is thoughtfully put together with some duplication and no major bugs. Group can speak to choices made in the code and knows what every line of code is doing.

### Testing

<!-- * 3: Project has a running test suite that tests multiple levels but fails to cover some features. -->
* 2.5: Project has sporadic use of tests at multiple levels. The application contains numerous holes in testing and/or many features are untested.


### Workflow

* 3: The group makes a series of small, atomic commits that document the evolution of their application and it is clear who was responsible for what features.
