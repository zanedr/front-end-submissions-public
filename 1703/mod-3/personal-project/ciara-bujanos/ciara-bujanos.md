## Project Name:  Smitten Kitchen
#### Check In: 1  

#### Project Pitch  Smitten Kitchen : the ultimate recipe cooking guide. It can access thousands of recipes from the Spoonacular Recipe API and allows users to save their favorite recipes.

### Deliverables  

#### Stack:  React, Redux, maybe backend, havent received API yet?

#### APIs:  https://spoonacular.com/food-api   if time integrate IBM Watson text to speech https://www.ibm.com/watson/developercloud/text-to-speech.html

#### Wireframes:  http://imgur.com/a/fFUcT

#### Waffle & Github:  https://waffle.io/buji405/smitten-kitchen    https://github.com/buji405/smitten-kitchen

#### Order Of Attack:  probably hook up the search bar, then work on login, logout, routing, finally save recipe button.

#### MVP:  

- user can search for a recipe by, cuisine, ingredients, and name of recipe.
- user can favorite recipes and view them. (not linked to the user)
- application is well tested
- tying everything to a user

#### Nice To Haves:

- ideally id like to incorporate a 'cooking mode' where you can have a text reader that reads recipes aloud as you cook.
- printing off the recipe
- ratings

#### Biggest Challenges: redux and backend if i need it.  

#### Deliverables for next checkin

- have boiler plate of front set up ( react, redux, router )
- have styles implemented
- if you get the API key back start making requests to get recipes
  - ideally search by name || cuisine easiest to knock out.
- look into [node.js]('http://frontend.turing.io/lessons/module-4/node.html') , [express]('http://frontend.turing.io/lessons/module-4/intro-to-express.html'), and [knex]('http://frontend.turing.io/lessons/module-4/knex-postgres.html')


#### Checkin 2

##
- have boiler plate of front set up ( react, redux, router )
     * Done - have all my containers rendering the components through router. 
- have styles implemented
   * homepage UI complete, working on the other route landing pages. 
- if you get the API key back start making requests to get recipes
  - ideally search by name || cuisine easiest to knock out.
       * I didnt get that API back yet, but I found another one to use that is similar and gave me the key immediately. I'm having a hard time doing a fetch call with it though so I have a screenhero with my mentor later today - hopefully he can help out. Biggest goal today is to get some info rendering. 
        
- look into [node.js]('http://frontend.turing.io/lessons/module-4/node.html') , [express]('http://frontend.turing.io/lessons/module-4/intro-to-express.html'), and [knex]('http://frontend.turing.io/lessons/module-4/knex-postgres.html')
  * havent had time to do this yet. trying to get api stuff going before I mess with backend. 


### Deliverables for Checkin 2 

- We need to figure out if the Node backend piece is worth it. I think it might be wise to consider cutting the user. 
I'm on the fence about that so I think if we you have everything with the API sorted out by friday we can still give this thing a run. If not you might have to do a lot of this stuff on the front end 

- Have API data coming through so that you can work with it. Even if it's just a single get requeste 
- have Tests set up so that you don't have to do this last minute. 
- It would be cool to have a random cooking quote appear on the page as the application is loading. 
