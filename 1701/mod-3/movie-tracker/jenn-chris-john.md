## EVAL REDO:



## PREVIOUS EVAL: MOVIE SPEC:

Notes: Chris Jordan late for eval

Bugs: 

- Can still login with the wrong password - should be responsability of backend

- No password comparison - can create account without passwords matching - could be on the front end

Minor Tweaks: 

- Password fields should behave like password fields (i.e. hide password, not show as plaintext)

- Don't commit a .DS_Store. Should always be reviewing PRs hard enough to not allow those types of files to be merged.


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

** Pending Fixing Password Issues **

* 4: The application meets all of the requirements listed above and implements one or more of the extensions.
* 3: The application consists of one page with all of the major functionality being provided by React. No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.
* 2: The application is in a usable state, but is missing 1 or more of the features outlined in the specification above.
* 1: The application is missing 3 or more smaller features or 1 major feature essential to having a complete application.
* 0: The application is unusable.

### Redux Architecture

When a reducer has a data type, it should always stay the same.

* 3: At least one component is not connected with Redux appropriately. Application state is mutated by more than just Redux. The Redux store is missing application data that it should be handling.

### Routing

Notes: Make sure you actually need to pass down history when you pass it down

* 3: Application is a single page and uses the React Router but does not display the appropriate components upon navigating.

### JavaScript Style

Lots of long methods that could have been broken out - long methods

* 2.5: Application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.

### Testing

Lots of unit tests - not very strong in the mounting - would like to see a few meatier tests

* 3: Project has a running test suite that tests multiple levels but fails to cover some features.

### Workflow

* 3: The group makes a series of small, atomic commits that document the evolution of their application and it is clear who was responsible for what features.
