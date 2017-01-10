# Instructor Evaluation Points: number-guesser
# Instructor: Meeka
# Comments:

### Bugs:

- Random number doesn't change when min and max are changed (questionable if bug - not sure how you handle this in the UI!)

- [Bug Fixed During Eval] Random number doesn't reset when you win the game (this is an actual game)

- Previous range taken into account when you reset the game (so if prev range was -1 to 2, your next random number would use that range but the user would see the default range)
  - Guessing the right number, if it's out of range, will be kicked back

### Notes: 

- Header file is not being used - site is all in application.js

- State is being used basically only as storage - you need to use state to drive components being rendered, rerendered, etc. Need to see use of props, components broken out logically by their structure. Avoid the trap of just splitting out functions - try to break the functions apart and split out units of HTML, basically. 

- Components to shoot for
  - Button should be a component that is reused for all buttons
  - Messages at top of page should be at least one component
  - Stretch Goal: is the input fields should be at least one component - and application.js html should mostly be just skeletal html and components being pulled in

  Think about it as the state will mostly live in application - so any functions that change state will mostly live in application and be passed as props to dummy components

# Rubric

# Functional Expectations

* 3.5: Application meets all of the functional expectations in Phase Two

# Fundamental JavaScript/React Style

* 2: Application runs but the code has long functions, unnecessary or poorly named variables, and needs significant refactoring
