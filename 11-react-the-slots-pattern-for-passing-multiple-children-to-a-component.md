# 11. The "Slots" Pattern for Passing Multiple Children to a Component

[Video Link](https://egghead.io/lessons/react-the-slots-pattern-for-passing-multiple-children-to-a-component)

This new app has a navbar component, and a body component, which has the side bar and the content. The navbar and the side bar need access to the user object so they could display the avatar.

The ```<Nav>``` component takes the user prop and passes it down to ```<UserAvatar>```,  Then ```<Body>``` takes the user prop and passes it to ```<Sidebar>```

```<Sidebar>``` takes user and passes it to ```<Userstats>```.  

**Taking a prop and forwarding it to children, then forward it to their children, is called "prop drilling."**

 You can use the React children prop to pass dynamic data into the ```<Nav>``` and ```<Body>``` components,

On the ```<Nav>``` component, replace user props with children. You can remove ```<Useravatar>``` as the render and render chidren. This makes ```<Nav>``` customizable. 

```javascript
const Nav = ({ children }) => (
    <div className="nav">
        {children}
    </div>
);
```

In the ```<App>``` component, we can pass in ```<UserAvatar>```, instead of the user prop. User is available inside of the render(), you can pass it into ```<UserAvatar>```.

```javascript
render() { 
const { user } = this.state;

return (
    <div className="app">
     <Nav>
       <UserAvatar user={user} size="small" />
     </Nav>
     <Body user={user} />
     </div>
    );
}
```
 
In the ```<Body>``` component. You have two Components, but you can only take one children prop.

Have ```<Body>``` take sidebar as a prop. Inside of ```<Body>``` make ```<Sidebar>``` a tag that renders sidebar inside of it.

Change the ```<Sidebar>``` function component to take children as props instead of user. Then have it render children inside the <div>.

```javascript
const Sidebar = ({ children }) => (
  <div className="sidebar">{children}</div>
);

const Body = ({ sidebar }) => (
  <div className="body">
    <Sidebar>{sidebar}</Sidebar>
    <Content />
  </div>
);
```

In the ```<App>``` component you can can pass in the ```<UserStats>``` directly into sidebar as props instead of user.

 Add 'main content here' to the ```<Body>``` component.

 ```javascript
 render() {
    const { user } = this.state;

    return (
      <div className="app">
        <Nav>
          <UserAvatar user={user} size="small" />
        </Nav>
        <Body side={<UserStats user={user} />}>
          main content here
        </Body>
      </div>
    );
  }
 ```

Back in the ```<Body>``` function component, add children as props. and pass the children down to the ```<Content> component.

```javascript
const Body = ({ side, children }) => (
  <div className="body">
    <Sidebar>{side}</Sidebar>
    <Content>{children}</Content>
  </div>
);
```

Change the ```<Content>``` component to take children, and render the children in place of that string. 

```javascript
const Content = ({ children }) => (
  <div className="content">{children}</div>
);
```

## Resources
[Dave Ceddia's Blog Post Pass 'Multiple Children to a React Component with Slots'](https://daveceddia.com/pluggable-slots-in-react-components/)














