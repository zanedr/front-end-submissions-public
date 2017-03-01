## Specification Adherence

3 - The application consists of one page with all of the major functionality being provided by jQuery. No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

## User Interface

Minor Bug: When entering a zipcode and then tabbing into an autocomplete option - then I have a 1 click lag on submitting when I hit enter. Same behavior does not happen when ignoring the autocomplete suggestions.

3 - The application has many strong pages/interactions, but a few holes in lesser-used functionality. The application less than 3 aXe-core violations

## HTML Style

Score bumped to a 3 after [this post eval PR submitted](https://github.com/zkc/Weatherly/pull/3)

** Previous **

Developers switched over to divs quite a bit - html is laid out semantically.

Would recommend going through and switching to semantic html instead of divs.

If changes made, will bump to 3.

2.5: Developer writes effective HTML, but does not write semantically correct and clearly organized code. Application shows some effort to use semantically correct HTML, but the divisions are inconsistent or unclear. There are many un-semantic tags and unnecessary selectors and it is not clear to the evaluator what a given section of code represents visually. Developer cannot speak to every line of code.

## CSS/Sass Style

4: Application has exceptionally well-factored CSS/Sass with little or no duplication and all styles separated out into logical stylesheets. There are zero instances where an instructor would recommend taking a different approach.

## JavaScript Style

3- Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

## Testing

Score bumped to a 2.9 after [this post eval PR submitted](https://github.com/zkc/Weatherly/pull/3)

Notes from PR review:

Sweet! Good work.

For the testing, to bump the score to a 3 I would still really want to see some juicier testing. I think this is basically the 'bare minimum' -- which is a huge improvement, but something that you need to keep an eye on continuing to grow as a developer.

Great submission, very professional - thank you for taking my feedback seriously!

** Previous **

Data wrapper or some kind of logical code should be broken into a js file and unit testing. 

Should have a test file per component with at least one test.

Make sure you don't have other components testing in random files.

Make more use of the test data.

If you get a pull request in to fix those things, will ammend score.

2 - Project has sporadic use of tests and multiple levels. The application contains numerous holes in testing and/or many features are untested.

## Workflow

3 - The developer makes a series of small, atomic commits that document the evolution of their application. There are no formatting issues in the code base.

## Code Sanitation

Score bumped to a 3 after [this post eval PR submitted](https://github.com/zkc/Weatherly/pull/3)

** Previous **

Do a little research into how to tell the linter in the eslintrc file that you're using React. Otherwise go with the disabling the specific rule.

DM with chosen fix when fixed and score will be ammended.

The output from a code sanitizer (either JSHint or ESLint) shows…

1 - More than ten complaints
