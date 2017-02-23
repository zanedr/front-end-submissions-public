### Student: Jeff Buss

#### Check In: 2

#### Project Name: ClandesDine

#### Client: Me, myself, Dan Grund

### Deliverables:  

##### Now that you have started building your app, what are the frameworks/additional modules/technologies/testing frameworks you are using, list those here (ALL of them). 

I decided not to utilize a prebuilt boilerplate. I don't want webpack/babel and all these packages we use to be black magic anymore. Instead I spent my whole weekend setting up my dev environment using the following:
 
*  webpack-dashboard
*  stage-0/ES7 (still having issues w/ babel not transpiling legacy decorators properly, but it's reading the property initializers w/in class constructors just fine)
*  react-redux-firebase
*  react-router-redux
*  redux-logger
*  redux devtools
*  redux thunk (not utilizing yet, but guessing it'll come in handy)
*  ESlint

##### Based on the MVP you stated in the first check in template, list what you have accomplished, and what still needs to be done.

As stated above I spent most of the weekend battling w/ setting up my dev environment, but still got a decent chunk done:

**Complete/in-progress**

* Form for submitting events is functioning. It appends to page, and is pushed to FB. On page load the data persists, and is being pulled from FB
* OAuth w/ Google is functioning, but having issues w/ routing the display of it based on whether the user is logged in or not
* Router is working for App rendering the navbar children (which would be the indexroute of home), but having issues linking to other pages
* Basic styling using MaterialUI

**ToDo**

* Set up routing based on user authorization. Only admins should see the add event section.
* Fix routing of OAuth/Events page based on whether user is logged in or not.
* Fix routing of pages besides the indexroute
* Set up invite code that links to a specific event alongside the google login
* Actually build pages:
	* Single event page
	* About
	* Media (likely instagram feed, am currently looking into packages for simplifying that)
	* Contact
* Consider RVP ideas

##### The next check in will be Monday/Tuesday. Based on unexpected challenges and/or unexpected progress adjust your MVP to reflect what you can get done by your next check in.  

* I believe I'll have my MVP basically done by Monday/Tuesday. Styling will still have a ways to go, but I can likely implement the above features by then.

##### What is on fire/what are you having trouble with?

* Router isn't working for routes past the index. Everyone I've asked has no idea, b/c it seems correct.
* Having issues w/ conditional rendering of the login/events page
* I'm using a handful of packages that are handling black magic I don't *fully* understand. It's a significantly different setup/file structure than what we've been doing in class, and need to do more reading/watching of videos so I can speak to my code fully.

### Screen Shots of Current State Of App  

[Screenshot](https://gyazo.com/72a77674078dc5c07c8eb4c0e644c5e7)


Expectations for Monday 2/27:
* Set up routing based on user authorization. Only admins should see the add event section.
* Fix routing of OAuth/Events page based on whether user is logged in or not.
* Fix routing of pages besides the indexroute
* Set up invite code that links to a specific event alongside the google login
* Actually build pages:
	* Single event page
	* About
	* Media (likely instagram feed, am currently looking into packages for simplifying that)
	* Contact
* Sign out
* Setting up Reducers.


