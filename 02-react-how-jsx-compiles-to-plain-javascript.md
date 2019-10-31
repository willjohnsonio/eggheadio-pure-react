# 01. How JSX Compiles to Plain JavaScript

[Video Link](https://egghead.io/lessons/react-how-jsx-compiles-to-plain-javascript)

The JSX you write in your React app actually get complied down to JS function call. When you look into the console in the browser you see the rendered HTML matches your JSX you wrote.

You can write this manually by returning ```<React.createElement()>``` and inside of it put your div, and tags using ```<React.createElement()>```. 

```javascript
function HelloWorld() {
    const name = 'Dave';

    return React.createElement(
        'div',
        null,
        React.createElement('h1', null, 'This is a Hello'),
        'hello',
        React.createElement('strong', null, name)
    );
}
```

As you can see in the code above React.createElement() take the element to create (div, h1, etc) as the first argument. The second arguement is the props you're passing in. The remaining arguments are the children of that div. 

The browser renders the the same thing as the previous JSX code.

**The React.createElement is what is running in the browser when you write JSX**

You can also render a custom component. Make a new function call name it custom, have it retun a ```<span>``` thats says custom. 

Then render it inside of our HelloWorld function and it will appear. We can also add one more arument to createElement after the strong tag. Pass in the custom component instead of a string without any props or children.

```javascript
function Custom() {
    return <span>custom</span>;
}

function HelloWorld() {
    const name = 'Dave';

    return React.createElement(
        'div',
        null,
        React.createElement('h1', null, 'This is a Hello'),
        'hello',
        React.createElement('strong', null, name),
        React.createElement(Custom)
    );
}
```
## Recap:
JSX gets compiled into React.createElement functions and createElement can create regular html elements by passing a string like div.

They can also render custom components by passing the function itself.


## Resources
[Introducing JSX React Docs](https://reactjs.org/docs/introducing-jsx.html)


