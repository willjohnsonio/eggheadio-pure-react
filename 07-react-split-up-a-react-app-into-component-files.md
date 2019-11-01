# 07. Split up a React App into Component Files

[Video Link](https://egghead.io/lessons/react-split-up-a-react-app-into-component-files)

**In a real React App it's usually one component per file.**

Cut the avatar componenet go to source (src) and create 'Avatar.js'. At the top of the file import react then export avatar as our default component.

```javascript
import React from 'react';

function Avatar({ hash }) {
  return (
    <img
      src={`https://www.gravatar.com/avatar/${hash}`}
      className="avatar"
      alt="avatar"
    />
  );
}

export default Avatar;
```
Back in index.js we need to import the Avatar component.

You can repeat this process with each component.

**VS Code has a feature where you can select a component. Hit the right click and refactor, and move it to a new file. It will create author.js that exports that component. It imports react for us.**

Go back over to index.js and import the component.

The VS Code feature export the the function instead of export default. 
export.

```javascript
export function Author({ author }) {
    const { name, handle } = author;
  return (
    <span className="author">
      <span className="name">{name}</span>
      <span className="handle">@{handle}</span>
    </span>
  );  
}
```

To import into index.js you need to wrap it in curly braces

```javascript
import { Author } from './Author';
```
This process for seperating components can be repeated. In this example for all the buttons. You create a new file called Button.js. 

Add all the buttons to the file and export the function like you did with Author.js. Import all the buttons serperated by commas inside of the curly braces.

```javascript
import { ReplayButton, RetweetButton, LikeButton, MoreOptionsButton} from './Buttons';
```
When you move the Tweet component into it' own file. You move all the imports it depends on into Tweets.js


## Personal Take:
I really like so far in the lessons you get to do some of same things over and over it's a great way to learn by doing. I can feel my understand getting clear with each lesson



## Resources
[Components and Props React Docs](https://reactjs.org/docs/components-and-props.html)

[Moment.js](https://momentjs.com/)






