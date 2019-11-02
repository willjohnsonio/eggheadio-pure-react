# 10. Use React Children to render dynamic content

[Video Link](https://egghead.io/lessons/react-use-react-children-to-render-dynamic-content)



You app an App component with ```<IconButton>``` as the child and it renders a button with some text. To customize it you have to write it manually 

Turn the ```<IconButton>``` tag into custom HTML tag where we can put some content.

Tthe content we put inbetween the ```<IconButton>``` tag is going to get passed in as a prop called Children. We can render the Children inside of button and it will change. 

```javascript
const IconButton = ({ children }) => (
    <button>
        <i className="fa fa-cloud" /> {children}
    </button>
);

const App = () => (
    <>
        <IconButton>Awesome</IconButton>
    </>
);
```

Make another component called ```<Alert>```. Pass children as props, render a div with the className of "alert". Then put in a icon with the className of "fa fa-exclamation-triangle. Then render the children under the icon.

```javascript
const Alert = ({ children }) => (
  <div className="alert">
    <i className="fa fa-exclamation-triangle" />
    {children}
  </div>
);
```

Put in the ```<Alert>``` component under the ```<IconButton>``` component and place some text inside to display.

```javascript
const App = () => (
  <>
    <IconButton>AWESOME</IconButton>
    <Alert
      title={
      Very <em>important</em> message!
    </Alert>
  </>
    }
);
```

To display more than one piece of dymanic content we can add props to ```<Alert>``` called title. Pass in "alert".

Then destructure the title prop and place the title inside of a ```<h3>``` tag above children.

```javascript
const Alert = ({ children, title }) => (
  <div className="alert">
    <i className="fa fa-exclamation-triangle" />
    <h3>{title}</h3>
    {children}
  </div>
);
```

You can pass JSX into a prop with curly braces.

You can't pass two elements next to each other, so wrap  the title props in fragment syntax.

```javascript
const App = () => (
  <>
    <IconButton>AWESOME</IconButton>
    <Alert
      title={
        <>
          <em>Hey! Listen!</em> Yeah you!
        </>
      }
    >
      Very <em>important</em> message!
    </Alert>
  </>
);
```














