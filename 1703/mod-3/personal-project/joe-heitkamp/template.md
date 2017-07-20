## Project Name:  Comic Connection, or Nerd Alert!

#### Check In: 1  

#### Project Pitch  

In the minds of most people, comic books are only full of brightly colored, spandex-clad, super-powered heroes and villains.  As a storytelling medium, comics are so much more.  From historically accurate visual journeys into the horrors of war, to deep philosophical and spiritual discovery, to murder mystery noir, comics have branched far from their super-powered roots to explore the wide breadth of storytelling that is usually thought to be reserved for literature or film.  Comic Connection is a comic book discovery portal to match a users interests with comics that they should check out.  While this may include superhero books, the idea is to expose people to the ever growing medium and help them create a connection that highlights the power of the medium to tell stories both super and sublime.

### Deliverables  

#### Stack:
* React
* React Router
* Redux
* Webpack
* Jest/Enzyme
* PostgreSQL

#### APIs:  
* [ComicVine](https://comicvine.gamespot.com/api/)
* [Goodzer](https://developer.goodzer.com/)

#### Wireframes  

#### Waffle & Github
* [Waffle](https://waffle.io/noetic97/comic-connection)
* [Github](https://github.com/noetic97/comic-connection)

#### Order Of Attack  

##### **Iteration 0**
- Postgres DB setup
- Api call to Comicvine that takes a dynamic user entry to determine the call endpoint
- Helper function to process and clean API data(will most likely need Promise.all)
- Display top 5 comic matches in a comic card w/ series synopsis

##### **Iteration 1**
- Allow user to select additional comics if more than 5 match their query
- Allow user to save comics they are interested in to a list of favorites
- Display saved/favorites in a separate view
- Saved/favorites will have the search keyword as a header so you know right away what type of interest it matches

##### **Iteration 2**
- New user signup form
- User login that allows favorites/saved to persist b/w sessions
- User must sign in to favorite/save a comic

##### **Iteration 3**
- Use a users location to allow them to find stores where they may be able to purchase the comics they have saved (Goodzer API)

#### MVP
- A user friendly search portal that returns a dynamic list of comic book series that map to a users chosen interests.
- application has a user saved in the backend along with favorites 
- user can filter comics by 10 genres
- slick UI

#### Nice To Haves   

 * Additional search/filter metrics - Superpowers, date ranges, writers/artists, etc
 * dynamically pass in genre 
 
#### Biggest Challenges  

The Comicvine API is overwhelmingly large with no easily defined keywords or genre markers to map to a users interests.

#### Instructor Notes

#### Deliverables for next checkin:
- have wireframes done. this will keep you accountable so that when you come up with new ideas you'll stick to what you've got 
- have backend setup (Node.js, express, knex, bookshelf)
    - frontend has a walk through on setting up the backend with knex and express thats great 
    - look into testing 
- Have initial app setup (react, redux, router) 
- either get the API to give you comics related to genres || scrape. 
    - nightmare.js, cheerio, selenium. 
