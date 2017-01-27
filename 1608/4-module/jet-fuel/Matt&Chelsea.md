# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

------

# Basics

#### Link to the Github Repository for the Project
[Repo](https://github.com/MilkMan90/JetFuel)

#### Link to the Deployed Application
[Application](https://jetfuelz.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Matt Kauffman](https://github.com/MilkMan90/JetFuel/commits/master?author=MilkMan90)

-[Chelsea Skovgaard](https://github.com/MilkMan90/JetFuel/commits/master?author=ChelseaSkovgaard)

#### Screenshot of your Application
<img width="716" alt="screen shot 2017-01-26 at 9 07 47 pm" src="https://cloud.githubusercontent.com/assets/18074889/22360299/c88bccc0-e40b-11e6-8859-2d0dd7fb5c7f.png">

## Completion

#### Were you able to complete the base functionality?

* Yes

#### Which extensions, if any, did you complete?

* No

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
* Why were you proud of this piece of code?
This was our own extension of generating a random string for the shorturl of our application.
```
function generateRandomString() {
  let characterArray = []
  for(var i = 0; i < 6; i++){
    characterArray.push(String.fromCharCode(97 + Math.floor(Math.random()*25) +1 ))
  }
  return characterArray.join('')
}

app.post('/api/urls', (request, response) => {
  const { actualurl, clickCount, folder_id} = request.body;
  let string = generateRandomString();

  database('urls').select('shorturl').then(function(res){
    console.log(res);
    let array = res.map((item)=>{
      return item.shorturl
    })
    while(array.includes(string)){
        string = generateRandomString();
        console.log(string);
    }
```

#### Link to a specific block of your code on Github that you feel not great about
* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

  We feel good about most of our code. One of our challenges was when we had to change how the ids of our urls were being created and had to drop and replace a column using migrations.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
  GET /api/folders
    ✓ should return all folders (48ms)

  POST /api/folders
    ✓ should create a new folder (38ms)

  GET /api/urls/:folder_id
    ✓ should return urls associated with a folder

  POST /api/urls
  [ anonymous { shorturl: '2' },
  anonymous { shorturl: '3' },
  anonymous { shorturl: '1' },
  anonymous { shorturl: 'lbisbm' },
  anonymous { shorturl: 'zxfhvv' },
  anonymous { shorturl: 'hwlboe' } ]
    ✓ should add a url

  DELETE /api/urls/:id
    ✓ should return urls associated with a folder

  GET /api/urls
    ✓ should return all the urls


  6 passing (146ms)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

-----

#### Please feel free to ask any other questions or make any other statements below!

-----

# Instructor Feedback

- Points: (base 150)
