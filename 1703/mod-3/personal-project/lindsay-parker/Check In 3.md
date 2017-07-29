## Project Name: “Back Home”

#### Check In:
3  

#### Project Pitch 
Provide an environment in which to view various architectural and interior design styles across multiple categories (exterior, by room, chairs, lighting, etc.).

### Deliverables  

#### Stack:
 - React
 - Redux
 - Router
 - Cheerio Web-Scraping
 - Enzyme/Jest

#### APIs:  
[Houzz](https://www.houzz.com/)

#### Wireframes  
![alt text](https://github.com/lindsaywparker/back-home/blob/master/comps/comp-summary.png "Back Home Static Comps")

#### Waffle & Github
[Waffle](https://waffle.io/lindsaywparker/back-home)

[GitHub](https://github.com/lindsaywparker/back-home)

#### Order Of Attack  
##### :white_check_mark: Iteration 0 - Landing Page
 - :white_check_mark: There should be buttons to view an individual style or category
 - :white_check_mark: There should be a button to view user favorites

##### Iteration 1 - By Style or Category
 - :white_check_mark: The user should see a random representation of each major style by category
 - :white_check_mark: When the user clicks a button to view individual style, **they should be brought to `/style/:style`** *(split into two items, based on the way I'm now displaying the styles matrix)*
 - When the user clicks a button to view individual **category, they should be brought to `/all/:category`** *(not sure on this one anymore..)*
 - These routes should display a random assortment of representative cards

##### Iteration 2 - By Style & Category
 - When the user clicks on an individual card, they should be brought to `/:style/:category`
 - This route should display a random assortment of representative cards

##### Iteration 3 - Favorites
 - There should be a button on each card to save it to Favorites
 - `/favorites` shows only favorited cards
 - User should be able to delete a favorite
 - If there are no favorites, there should be a message indicating that there are no favorites

#### MVP
Grid of random category-by-style representations with ability to click style or category and bring up new representations

#### Nice To Haves
 - User favorites should persist
 - `/favorites` should show a calculated style tendency based on the users selected favorites
 - Search functionality
 - Filter functionality
 - Photo browser
 - Implement a `More` button on style and category pages
 - Clicking an item directs to ???
 - Shuffle button on `/:styles` that shuffles the individual representation

#### Biggest Challenges
 - Redux again
 - Web Scraping

#### Instructor Notes
 * Scraper =>  Node, Express.
 * React, Redux, Router, Enzyme/Jest
 * Favorite? 
 
#### Deliverables for next checkin:
 * Finish iteration 2 by Thursday and have written more tests / worked on UI/UX.
   * Tests might be hard due to the nature of react router so do as much as you can!
