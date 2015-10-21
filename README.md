# **Node/Express/Git Tutorial**
___
# Part 1: Installation(s)
___
#### Step 1
Install [Node.js](https://nodejs.org/en/download/)
node is a framework that allows for JavaScript to be run on your computer.
It also allows for low-level networking (which you will use to run a local server on your machine).
node also comes with npm (node package manager).
The package manager allows for you to install whatever module/add-on to node (as opposed to finding it on the internet and installing it manually. think of the package manager for Linux).

#### Step 2
Go to github.com and create a new repo for yourself and name it whatever.

#### Step 3
Clone the repo to any directory on your computer using either GitHub desktop or the Git shell (directions for Git shell should be on your new repo page)

#### Step 4
Open up the command line and navigate to your local repo/directory using 'cd'.
Alternatively, navigate to the directory in the file explorer and `shift + right click` on "Open command window here".

#### Step 5
Enter `npm init` into the command line. This will begin the process of creating the file "package.json", which contains metadata that allows for npm to identify your project as a project and to handle dependences.
You can hit return for all the prompts to accept the defaults.

#### Step 6
Although we have installed Node.js, we will not be directly working with it. We're going to install another framework called Express.js, which does some abstraction on top of Node and is geared towards web applications. 

Enter `npm install express --save`. What this does is that it installs Express to your app (AKA the directory we're in) and adds it to the dependencies section of your 'package.json' file.
___
# Part 2: Actually Writing Stuff
___
#### Step 1
Within your app directory, create:
- A JavaScript file: I typically name it "app.js"
- An HTML file: I typically name this one "index.html".

Naming the HTML file "index.html" follows the convention of servers automatically looking for a file named "index.html" and displaying it whenever there is no file name in the URL. Following that convention, our express server will also listen for the URL `"/"` (meaning that complete URL is just some-website.com/) and display the file `index.html`.

#### Step 2
Write whatever you want in the HTML file. It doesn't even have to be HTML for now. I usually write "poop".

#### Step 3
Within your `app.js`, enter the following code:
```
var express = require('express');
var app = express();

app.get('/', function(req, res) {
	res.sendFile(__dirname + '//index.html');
})

app.listen(80); // internet browsers by default will go to port 80.
```
- `require` loads the express module into the JS file.  
- `var app = express()` initializes the Express application/server.  
- 'app.get' will retrieve `'/'` URLs and takes a callback function.  
- The callback function takes `req` and `res` (request and response) as parameters.  
- `res` is an object that represents the HTTP response that is sent to the client.  
- `sendFile` needs an absolute path to the HTML file that we will be sending.
- `__dirname' is a global constant provided by Node.js that represents the root directory path.
- `app.listen(80)` will start the server on port 80, which is the port that browsers go to by default.
___
# Part 3: Syncing
___
#### Step 1
Save everything.
#### Step 2
If you aren't already familiar with git, go through this [Git tutorial](https://try.github.io/levels/1/challenges/1) and/or [this one](https://guides.github.com/activities/hello-world/).
#### Step 3
Your local git repo is now obviously different from your remote repo. Push your local changes to the remote repo.

















