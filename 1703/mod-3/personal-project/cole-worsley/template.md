## Project Name: Workout App (Pending Title)  

#### Check In: 1  

#### Project Pitch  
A workout app that generates randomized exercises from the WGER API. As you build your history, you will have the option to choose which workouts you enjoy more than others. The app will be more likely to repeat those preferred exercises while adding in similar ones.

### Deliverables  

#### Stack:
* React
* Redux
* Router
* Node
* Express
* Knex / Bookshelf
* Postgres

#### APIs:  
[WGER](https://wger.de/en/software/api)


#### Wireframes  
![Dashboard](https://github.com/coleworsley/front-end-submissions-public/blob/master/1703/mod-3/personal-project/cole-worsley/Dashboard.png)
![MainPage](https://github.com/coleworsley/front-end-submissions-public/blob/master/1703/mod-3/personal-project/cole-worsley/Desktop%20HD.png)


#### Waffle & Github
[Waffle](https://waffle.io/coleworsley/Work-Up)
[GitHub](https://github.com/coleworsley/Work-Up)

#### Order Of Attack  
* Build out boilerplate code. Perhaps set up express to start and begin by making a couple of fetch calls.
* Start by making fetch calls to the API and building out main workout page
* Display individual exercises detail page
* learn express and build out backend to hold workout history and likes and dislikes logic.
* Add in user authentication for sign in to make Challenges
* build out main dashboard on home page
* Add logic to make the randomizer smart


#### MVP
* Project displays randomized workouts and exercises
* Project saves a user and gives prefered workouts to the front-end 


#### Nice To Haves   
* Graphs built with D3. Will start with RE-Charts and if I feel up to it, will attempt to build them with D3.
* Maybe a map component? Not sure but could be cool and everyone likes maps apparently

#### Biggest Challenges  
* Building the backend
* Potentially the Graphs
* Design

#### Instructor Notes
- nice to haves: OAuth

#### Deliverables for next checkin:

- Have node backend setup with knex, maybe bookshelf, 
    - have user table and the workout table setup 
    - go through front end lessons on knex, node / express
    - look into backend unit-testing. (it's super easy i Promise.all)
- bare bones of the front-end 
    - react, redux, router, 
 - tighten up your wireframes. 
