## Project Name: The Bearded Bartender (to be hosted at http://www.thebeardedbartender.com)

#### Check In: 1  

#### Project Pitch
* Have you ever had guests over and wanted to make them drinks, but looked in your home liquor cabinet only to think to yourself, "What the hell can I make with this stuff?" Well, fret no more! With The Bearded Bartender at your side, you'll wow your friends and land all the hot dates as you are transformed from the clueless host slinging jack & coke's to Tom Cruise in the movie Cocktail (looks may vary).

### Deliverables  

#### Stack:
* React/Redux/Router/CSS3 for the front-end application
* Node.js/Express/KNEX for the backend server
* postgres for the database

#### APIs:
* MVP: [Absolut Drinks Database API](https://addb.absolutdrinks.com/docs/)
* Future: [The Cocktail DB](http://www.thecocktaildb.com/)
* Future: Drizly

#### Wireframes  
![Landing Page](https://github.com/the-oem/bearded-bartender/blob/master/comps/landing-page.jpg?raw=true)

![Filter Results](https://github.com/the-oem/bearded-bartender/blob/master/comps/filter-results.jpg?raw=true)

![Detail View](https://github.com/the-oem/bearded-bartender/blob/master/comps/detail-view.jpg?raw=true)

#### Waffle & Github
* [GitHub Repository](https://github.com/the-oem/bearded-bartender)
* [Waffle Board](https://waffle.io/the-oem/bearded-bartender)

#### Order Of Attack  
##### Iteration 0
* (complete) Database Schema for users and favorites
* (complete) Wireframes for application
* (complete) Running Node API with end-points for creating account, validating user (login), getting favorites, adding favorite, deleting favorite

##### Iteration 2
* Base application with ability to create account & login
* Create account and login tests

##### Iteration 3
* Hooked up to ADDb and pulling drink recipes from user search
* Search and drink rendering tests

##### Iteration 4
* Displaying drink with image, ingredients and instructions
* Drink details rendering tests
* Users can favorite drink recipes & view their favorites list
Favoriting & favorite listing tests
* Users can view embedded videos teaching how to make the drink

#### MVP
* Users can register for an account & login
* Users can search drinks (by name)
* Users can view drink recipe details
* Users can favorite drink recipes, which show up in a favorites list

#### Nice To Haves   
* Users can search ingredients (by name)
* Users can filter drink recipes by occasion/ingredient
* Users can maintain a list of ingredients they own
* Users can find out what recipes they can make based on their stock of ingredients
* Users can enter their own personal recipes
* Users can upload and tag photos of the drinks they make
* Users can share their favorite recipes on social media
* Users can search drink recipes (by any ingredient)
* Users can login using a social media account
* Integrate with Drizly to allow for users to do one-time orders for ingredients or set up a recurring schedule to be delivered.

#### Biggest Challenges  
* Building a proper data model for the backend API's
* Learning Node.js/Express/KNEX
* Testing. Because...testing.

#### Instructor Notes
* Search
* Favorite drinks - KNEX
* Sign in user -> KNEX
* Filtering, by class, drink - extension


* Maintain own ingredients - Stretch
* What cocktails can you make from you cabinet - Stretch

#### Deliverables for next checkin:
* Users can create an account
* Users can login / logout
* Login persists to local storage
* User can see all drinks pulled from ADDb
* User can favorite / unfavorite a drinks
* Tests for all the above
