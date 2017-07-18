## Project Name: “Back Home”

#### Check In:
1  

#### Project Pitch 
Provide an environment in which to view various architectural and interior design styles across multiple categories (exterior, by room, chairs, lighting, etc.).

### Deliverables  

#### Stack:
 - React
 - Redux
 - Router
 - API or Web-Scraping (dependent on API approval & content)
 - Enzyme/Jest

#### APIs:  
[Houzz](https://www.houzz.com/)

#### Wireframes  
![alt text](https://github.com/lindsaywparker/back-home/blob/master/comps/comp-summary.png "Back Home Static Comps")

#### Waffle & Github
[Waffle](https://waffle.io/lindsaywparker/back-home)

[GitHub](https://github.com/lindsaywparker/back-home)

#### Order Of Attack  
##### Iteration 0 - Landing Page
 - The user should see a random representation of each major style by category
 - There should be buttons to view an individual style or category
 - There should be a button to view user favorites

##### Iteration 1 - By Style or Category
 - When the user clicks a button to view individual style or category, they should be brought to `/:style` or `/all/:category`
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

#### Biggest Challenges
 - Redux again
 - API Calls / Web Scraping

#### Instructor Notes

#### Deliverables for next checkin:
