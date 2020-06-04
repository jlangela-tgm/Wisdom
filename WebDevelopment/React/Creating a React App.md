# Creating a React App

## Setup

Create the app inside of your projects directory by typing

````powershell
npx create-react-app <project name>
````

now `cd` into the directory and and launch the app

````powershell
cd <project name>
npm start
````

## Creating a Component

### Creating a new Class

In order to create a Component, you will need to do the following:

* Create a new .js file
* import React
* create a new Class
* export it at the end of the file

````react
import React, {Component} from 'react';

class Application extends Component{
	// Code Ommitted
}

export default Application;
````

### Rendering HTML

For your component to render HTML you will have to implement the render function and return the HTML.
Inside of the render function you can declare variables, which can be inserted into the rendered HTML using `{variable}` Syntax.

````react
render(){
	let name = "Jan";
    return(<h1>Hello {name}</h1>);
}
````

The rendered HTML can only contain one root Tag, in order to render multiple HTML Tags you will need to surround them with a `div` tag.

````react
render(){
	let name = "Jan";
    return(
        <div>
        	<h1>Hello {name}</h1>
            <p>How are you doing?</p>
        </div>
    );
}
````

## Lifecycle functions

Video 5