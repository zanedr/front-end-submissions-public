## Students & Project: 
## Evaluator:
## Notes:


**WEATHER SPEC**:

```
Iteration 0: Current Location
* Use the Geolocation API to determine your current location.


Iteration 1: Sunrise & Sunset
* At the top of the app you should display the sunrise and sunset information with icons.

* Based on that information, and the current time, your UX should change to indicate whether it is morning, noon, evening, or night.

Iteration 2: Current Weather Header
* Create a header bar that displays your current city’s temperature (in Fahrenheit) and weather description (e.g. ‘windy’, ‘rainy’, ‘sunny’)

Iteration 3: Settings Page
* Create a `/settings` route that displays an input field to enter a city’s zip code and save it as a “pinned” city. User should be able to delete cities.  

Iteration 4: Pinned Cities Dashboard
* Create a dashboard/index page that shows the Current Weather for a maximum of 3 “pinned” cities.
* If there aren’t 3 pinned cities, add a placeholder with a link to “Pin a new city”

Iteration 5; Pinned City Show Page
* Each pinned city forecast on the dashboard should include a link to display an extended 5 day/3 hour forecast.
* The route for the extended forecast should be something like /forecast/<cityId>.
```


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
* 3: The application consists of one page with all of the major functionality being provided by React. No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.
* 2: The application is in a usable state, but is missing 1 or more of the features outlined in the specification above.
* 1: The application is missing 3 or more smaller features or 1 major feature essential to having a complete application.
* 0: The application is unusable.

### Redux Architecture

* 4: Appropriate components are wrapped in connected Redux container components. The Redux store contains all necessary application data and nothing more. All state changes are handled through Redux actions and reducers.
* 3: At least one component is not connected with Redux appropriately. Application state is mutated by more than just Redux. The Redux store is missing application data that it should be handling.
* 2: Application state is mostly outside the control of Redux. Application did not make use of Redux actions and reducers to mutate state. Components do not demonstrate a clear understanding of stateful vs. statelessness.
* 1: Application does not make use of Redux to manage state. There are little or no connected components.

### Routing

* 4: Application is a single page and uses the React Router to display appropriate components based on URL.
* 3: Application is a single page and uses the React Router but does not display the appropriate components upon navigating.
* 2: Application does not render/cannot find additional routes.
* 1: Application did not use a Router


### JavaScript Style

* 4: Application has exceptionally well-factored code with little or no duplication and all components separated out into logical components. There are zero instances where an instructor would recommend taking a different approach.
* 3: Application is thoughtfully put together with some duplication and no major bugs. Group can speak to choices made in the code and knows what every line of code is doing.
* 2: Application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.
* 1: Application has a significant amount of duplication and one or more major bugs. Group cannot speak to most choices and does not know what every line of code is doing.


### Testing

* 4: Project has a running test suite that exercises the application using Enzyme. The test suite covers almost all aspects of the application including the Redux actions and reducers.
* 3: Project has a running test suite that tests multiple levels but fails to cover some features.
* 2: Project has sporadic use of tests at multiple levels. The application contains numerous holes in testing and/or many features are untested.
* 1: There is little or no evidence of testing in this application.

### Workflow

* 4: The group effectively uses different Git branches, submits pull requests and reviews each other’s code. The evolution of the application and who was responsible for what features is clearly documented through github.
* 3: The group makes a series of small, atomic commits that document the evolution of their application and it is clear who was responsible for what features.
* 2: The group makes large commits covering multiple features that make it difficult for the evaluator to determine the evolution of the application and who worked on what features.
* 1: The group committed the code to version control in only a few commits. The evaluator cannot determine the evolution of the application.
* 0: The application was not checked into version control.
