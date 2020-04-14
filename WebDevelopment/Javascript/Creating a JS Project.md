# Creating up a Node.js Backend

## Setup

> https://www.robinwieruch.de/javascript-project-setup-tutorial/
>
> https://www.robinwieruch.de/minimal-node-js-babel-setup

First create the Project folder

````powershell
mkdir my-project
cd my-project
````

Now we initialize the Project using ``npm``

````powershell
npm init -y
````

The `-y` Attribute tells `npm` to use the default Settings, these can be viewed and changed later by using the following commands.

````powershell
npm config list
npm set init.author.name "Jan Langela Regincos"
npm set init.author.email "jlangela@student.tgm.ac.at"
npm set init.author.url "example.com"
npm set init.license "MIT"
````

Next up create a `src/` Folder, this can either be done in your IDE, GUI or in using the CLI. The `src/` Folder will contain all of your projects source code.

````powershell
mkdir src
cd src
echo > index.js
````

Now let's type some code into the `index.js` file to test it.

````javascript
console.log('Hello World!');
````

Let's execute it by typing

````powershell
node src/index.js
````

The log should appear in your Command Line.

Next we'll move the script into the `package.json` file, that's where all of the projects scripts (start, test, deploy) will end up in.

````json
{
  ...
  "scripts": {
    "start": "node src/index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  ...
}
````

## Nodemon

With our current setup, in order to try out our source code we always need to start our script. A neat way to work around this, is by using an always running node process. This is done by installing the `nodemon` library as a development dependency to our project.

````powershell
npm install nodemon --save-dev
````

Next, we'll exchange node with nodemon in our npm start script

````json
{
  ...
  "main": "index.js",
  "scripts": {
    "start": "nodemon src/index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  ...
}
````

When we run our application with `npm start` from the  command line, it should keep running. The best part is that the script  will execute again once we change the source code. Lets adjust the source code in the *src/index.js* file and see what happens in the command line.

````javascript
console.log('Hello ever running Node.js project.');
````

## Babel

In order for our Node.js project to be capable of using recent JavaScript features that are not included in the recent Node.js versions, we need to install Babel for our development dependencies.

````powershell
npm install @babel/core @babel/node --save-dev
````

Next, let's add it to our npm start script:

````
{
  ...
  "main": "index.js",
  "scripts": {
    "start": "nodemon --exec babel-node src/index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  ...
}
````

Under the hood, Babel transpiles the code to vanilla JavaScript. When we use an upcoming JavaScript language feature, which  hasn't been introduced in Node.js, we can still use the feature in your source code. Babel makes sure that Node.js understands it. However,  there is still one crucial step to include upcoming language features  with Babel. We can activate different upcoming JavaScript features by adding them as presets to Babel. Let's add the most common used Babel  preset to your application: