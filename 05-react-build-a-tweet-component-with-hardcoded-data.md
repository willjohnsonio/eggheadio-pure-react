# 05. Build a Tweet Component with Hardcoded Data

[Video Link](https://egghead.io/lessons/react-build-a-tweet-component-with-hardcoded-data)

In the previous lesson you looked at a sketch of the tweet component you're going to build.

Start off building this component by importing React and ReactDOM. Then use ReactDOM.render to render the tweet. Then you'll use document.querySelector and attatch it to the root element.

Then create the tweet component that will return a div with the class of tweet with some text

```javascript
import React from 'react';
import ReactDOM from 'react-dom';

function Tweet() {
 return <div className="tweet">hi</div>;
}

React.DOM.render(
    <Tweet/>, 
    document.querySelector('#root'))
```

The next thing you'll do is import the CSS file. Importing it will cause the webpack to bundle the CSS with yor project. By inserting the style tag when it renders. 

The rest of the lesson is creating and and using components.








