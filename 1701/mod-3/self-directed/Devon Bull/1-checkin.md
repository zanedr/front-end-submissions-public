### Student: Devon Bull

### Project Name: Unavee  
      
#### Check In: 1  

#### Collaborators:  
Flyin solo. 

#### Project Pitch  
Build an simple mobile app in React Native that: allows you to search for someone using the FullContact Api, 
returns the results in a format to learn about and connect to the individual along with a personality insight from the Watson Api.

Would be an awesome way to experiment with pulling data from multiple sources using Express since Full Contact is returning a cors error in the browser.


### Deliverables  

Explore and understand React Native. Learn how to work with cors. Interact with the Watson api. Learn more about Express.
Deliver a project that primarily works well. UI is cool but the technical aspects provide more opportunity for growth. 

#### Stack: 

React Native. Express. 

#### APIs:  
Links to any API docs that you have decided to use:

[FullContact](https://www.fullcontact.com/developer/docs/)

[Watson](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v3#!/personality45insights/profile)

#### Wireframes  
Include screenshots to wireframes or comps of **EVERY PAGE** of the MVP of your app. You can include these by adding additional files to your submissions directory, or linking to an imgur account. You're asked to use Sketch, or Balsamiq, or a different digital wireframe/comp application but if you choose to use pen/paper please let your instructors know and bring those to class Monday.  

![Main Plan of Attack](http://i.imgur.com/q0sMfW0.png)

![Watson Possible Screenshot](http://i.imgur.com/YiDJbZR.png)

#### Waffle.io
Link to your waffle.io account with at least 10 cards indicating baby steps to how you want to structure your attack.  

[Wafflie.io Unavee](https://waffle.io/DBULL7/Unavee)

### Reflection  
This project scares me a bit and that's a good thing. I don't yet know how I'm going to overcome certain challenges. But I will. 

#### Order Of Attack  
Based on your wireframes, in what order are you going to approach building out this application?

I might start in regular React and get the Full Contact API working through the Express server first.
If I can display and organize those results I can then start on React Native, and from there move on to Watson. 


#### MVP
React Native app that returns the results of a search from Full Contact with the ability to click on links from the results (to LinkedIn or something).

#### Nice To Haves   
Option to save searches to a database, say Firebase (which looks awesome!). Perhaps also Firebase authentication. 
Maybe suggest nearby meetups?? Or take photos (of say business cards) to store in Firebase?


#### Biggest Challenges  
What do you forsee being the biggest challenges of this project? List at least 3 resources you've thought of to help overcome these challenges.

1: Working in Express: I reached out to Pam in M4 for advice and she provided me with a link to a lesson on Express that she found helpful. I've also previously read the Express docs.

2: Navigation in React Native: the docs are bad and it was painful when I tried it a week and a half ago. But I got it to work and should be able to figure out the docs 🙏
The RN env is also tricky since I haven't figured out how to console log (if that is even possible). 

3: Watson. I've referenced the Api docs but it still seems a bit confusing and the post request body requires a very specific format. 
I might also not get enough information back from the Full Contact search and may need to use something like the Twitter Api to get more data for Watson. Resources: Online tutorials/reading the docs/talking to Pam.

4: Full Contact has a fairly short API limit for Person with 250 user returns. Can slightly get around this using other calls but the Person api seems to have the most crucial data. 
Maybe Jeff or an instructor knows someone there?


Taylor: 

MVP:
Express API, React front-end using Router and Redux
A user should be able to:
Search emails/twitter handles and be redirected to a users page. 
~Favoriting a user for later lookups.
Tested application
UI/UX

Extension: 
Saving favorites inside a database. -> This would require you to flush out your api to use a backend database like PSQL. 
Look into KNEX.

Check In 2, Thursday 5/25:
* Express setup.
* Creating your endpoint for your api `/api/v1/user?email=tman2272@aol.com
* Using Request try and hit FullContact api. 

Check In 3, Tuesday 
React Router setup
5 Tests

Check In 4, Thursday

* Implement a database Knex database
* TESTS
* Implement redux

