# 01. Write Your First React App: Hello World!

[Video Link](https://egghead.io/lessons/react-write-your-first-react-app-hello-world)

In the terminal run create react app and the file name for this example it will be 01-hello-world. 

```<create-react-app 01-hello-world>```

Once Create React App is done installing,run```<cd 01-hello-world>```. Create React gives you a bunch of files inside of the src folder that you won't need. Access the src folder and delete everything inside of it. Use these terminal commands. 

```<ls src>```
```<rm src/*>```

Now you create your own index.js file using the touch command. 

```<touch src/index.js>```

Go to the terminal in your code editor run ```<yarn start>```. That will start a development server and show up in our browser.

In index.js import React from 'react' , next import ReactDOM from ReactDOM package.

```javascript
import React from 'react'; 
import ReactDOM from react-dom;
```

So that you can render something to your page you call ReactDOM.render(). The first arguement you put is the string 'hello' and the second arguemnt is where you want it to render to. 

Create React App comes with a index.html file it contains a ```<div>``` with the ID of 'root' That's where we will display our React app.

```javascript
ReactDOM.render('hello', document.querySelector('#root')
);
```

Right now 'hello' is just a string, you can wrap 'hello' into HTML tags like ```<div>``` and it will display the same. Using the HTML this way is a syntax called **JSX**.

```javascript
React.DOM(
    <div>Hello</div>,
    document.querySelector('#root')
)
```

You can also make a JavaScript function and return the div inside of it. Inside of ReactDOM.render we display the ```<Hellworld>``` like an HTML tag.

```javascript
function HelloWorld() {
    return <div>hello world</div>;
}

ReactDOM.render(
    <HelloWorld/>,
    document.querySelector('#root')
)
```

You just created a React component! React components start with captial letters and use pascal case.

Outisde of JSX this is all JavaScript. This component is normal function that returns some JSX. 

Any valid HTML can work we can add ```<strong>``` tags and all.

**We can only return a single tag from a component.**

You can't type a second ```<div>```. If you did you would get an error.

**One thing you can do with JSX that you can't do with HTML is dynamic content.**

You declare and define a variable called name. Remove the word 'world, add some curly braces put the variable 'name' inside the curly braces. 

Now the screen will display Hello and whatever you set the name variable to.

```javascript
let name = Bane;

function HelloWorld() {
    return <div>hello {name}</div>;
}

ReactDOM.render(
    <HelloWorld/>,
    document.querySelector('#root')
)
```

**You can place any JavaScript Expression inside of the curly braces**