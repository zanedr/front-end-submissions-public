## Project Name:  Fatal Force

#### Check In: 2

#### Project Pitch  

### Deliverables  

#### Stack:
- React, Redux, Router(maybe if necessary), Victory.js, Enzyme/Jest

#### APIs:
- [The Counted API](https://www.thecountedapi.com/)
- [Google Maps Javascript API](https://developers.google.com/maps/documentation/javascript/)

#### Wireframes: Image included in file

#### Waffle & Github
- [Waffle](https://waffle.io/tlgreg86/theLost)
- [Github](https://github.com/tlgreg86/Fatal-Force)

#### Order Of Attack


+ ##### Iteration 0

 - The data should be getting called and saved to state.
 - Should be rendering the data on the screen.
 - '/' should route the user to the homepage with all of the data rendering there.

+ ##### Iteration 1

 - Should have the ability to search/filter data based on categories in the API.
 - '/visualizations' should take the user to the visualizations page where they can see and manipulate different visualizations of the API's data.
 - visualizations page should have 3 different charts displaying the data.

+ ##### Iteration 2

 - Visualizations page should have google map that has been modified to represent the data for each state.
 - User should be able to select data by year on vis page.

#### MVP

 - My MVP will have a page that renders a filterable grid of the victims of fatal police encounters as well as a second page using router that uses D3 to visualize the data.

 - Visualize data with googlemaps

 - filter by params (state, sex, address)

 - generate a link to the filtered data.

#### Nice To Haves

 - Print report

 - Multiple different visualizations that can be filtered by the user.

 - Have images.

#### Biggest Challenges

- Implementing the google maps javascript api

- Implementing Victory.js in to react/Redux

- Testing

#### Instructor Notes

#### what was completed:

- have boilerplate set up (react, redux, router)

    - [√] application should be pulling in data

    - have one chart built out for me

    - have 2 routes

      - the app is still breaking when I try to connect router in my index.js

    - [√] have cards rendering data with name and location.

- look into getting images.

#### Deliverables for next checkin 7/24

* router should be completely hooked up 
   - do this first! 
   - you'll need this for the transferable link 
* have atleast 2 - 3 charts built out for me. 
    - this is the crux of your project so I would assume we have this going 
* app should be styled. 
* fetch mock tests
 
