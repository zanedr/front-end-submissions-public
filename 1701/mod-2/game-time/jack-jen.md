# Instructor Evaluation Points: Game Time
# Instructor: yung-jhun
# Comments:

- Game is functional.

- Would like to see more integration tests ( tests that communicate what is actually going on. Not just pulse checks but you replicating situations in the game and asserting you are getting the output you want.)
  - loved the one test that was automated.

- Game knows too much
  - Should probably move collision detection to the ball (for its collisions), and move to board (detecting sides and so forth)
  - If that doesn't make sense you could theoretically move all the collisions to another class to handle the specific collisions like to happen. ( I think the prior suggestion is better...)


## Functional Expectations

* 3 - Application is fully playable without crashes or bugs

### User Interface

* 3 - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

### Testing

* 3 - Project has a running test suite that tests multiple levels but fails to cover some features. All functionality is covered by tests. The application makes some use of integration testing.

### JavaScript Style

* 3 - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

### Workflow

* 4 - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

### Code Sanitation

The output from JSHint shows…

* 4 - Zero complaints
