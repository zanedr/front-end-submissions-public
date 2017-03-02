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

### Specification Adherence  

* 4: The application meets all of the requirements listed above and implements one or more of the extensions.

### Redux Architecture

* 3: At least one component is not connected with Redux appropriately. Application state is mutated by more than just Redux. The Redux store is missing application data that it should be handling.

### Routing

* 4: Application is a single page and uses the React Router to display appropriate components based on URL.


### JavaScript Style

* 3: Application is thoughtfully put together with some duplication and no major bugs. Group can speak to choices made in the code and knows what every line of code is doing.


### Testing

* 3: Project has a running test suite that tests multiple levels but fails to cover some features.

### Workflow

* 4: The group effectively uses different Git branches, submits pull requests and reviews each other’s code. The evolution of the application and who was responsible for what features is clearly documented through github.
