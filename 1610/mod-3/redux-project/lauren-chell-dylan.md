## Students & Project: Lauren, Chelle, Dylan || Movies
## Evaluator: Brittany
## Notes: Great job refactoring and getting the app into a working state over the last couple days of the project. Demonstrated a much clearer understanding of React/Redux architecture, and was able to solve bugs previously reported. Routing issues were resolved and worked splendidly. Testing should be slightly less linked to the HTML/DOM Content, but solid effort put in across the board there.


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

* 4: The application meets all of the requirements listed above and implements one or more of the extensions.

### Redux Architecture

* 4: Appropriate components are wrapped in connected Redux container components. The Redux store contains all necessary application data and nothing more. All state changes are handled through Redux actions and reducers.

### Routing

* 4: Application is a single page and uses the React Router to display appropriate components based on URL.

### JavaScript Style

* 3: Application is thoughtfully put together with some duplication and no major bugs. Group can speak to choices made in the code and knows what every line of code is doing.

### Testing

* 3: Project has a running test suite that tests multiple levels but fails to cover some features.

### Workflow

* 3: The group makes a series of small, atomic commits that document the evolution of their application and it is clear who was responsible for what features.
