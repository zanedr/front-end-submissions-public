# Instructor Evaluation Points: shoot the breeze
# Instructor: Meeka
# Comments:

All components must be tested using Enzyme - You do not need to test authentication. - Note: sort is tested through application but ChatMaster is not tested. 

Submit and Clear are disabled when there is no content in the message input - Note: visual change for disabled buttons would make things clearer

Submit is disabled when the message is over 140 characters: Character count color change is a really nice touch

### Based on comps - the following differences are noted:
- Change of text for users in the user component (reads: 'Users Present in the Chat Room')
- List of users is shown as button
- Logged in user does not have a red indicator beside their name in sidebar user component
- Email is shown for users 
- Text instead of arrows for the sort buttons
- displays first and last name and not just first name
- Log out was not in the spec but was added
- Messages should still show if logged out (currently don't)
- Mobile view - the name of the app is still present
- Mobile view - date should be shortened
- Mobile view - character count should be beside the message bar 

# Specification Adherence

* 3.5 - The application consists of one page with all of the major functionality being provided by React. No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

(extension was done (log out) but not communicated - however, we have not communicated very well that communicating should be communicated)

# Component Architecture

* 3 - Application is broken in out into at least 8 components that properly encapsulate functionality. There is no more than one component that could be broken down into composite parts.

# User Interface

* 3 - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

# CSS/Sass Style

* 4: Application has exceptionally well-factored CSS/Sass with little or no duplication and all styles separated out into logical stylesheets. There are zero instances where an instructor would recommend taking a different approach.

# JavaScript Style

* 3- Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

# Testing

* 3 - Project has a running test suite that tests and multiple levels but fails to cover some features. All functionality is covered by tests. The application makes some use of feature testing.

# Workflow

* 3 - The developer makes a series of small, atomic commits that document the evolution of their application. There are no formatting issues in the code base.

# Code Sanitation

The output from a code sanitizer (either JSHint or ESLint) shows…

* 3 - Five or fewer complaints

Note: 1 uniq complaint

# Design

* 3 - The application has a strong approach to layout and content hierarchy, but typography and color choices are lacking. The evaluator has several recommended changes to improvement.