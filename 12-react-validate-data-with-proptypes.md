# 12. Validate data with PropTypes

[Video Link](https://egghead.io/lessons/react-validate-data-with-proptypes)

React has a feature called PropTypes. It will add typing to React components that'll show warnings, if they don't recieve the props that they expect. You3 add the package manually. Then import that package at the top of the file.

```javascript
yarn add prop-types
```

Go the the  ```<LikeButton>``` component. Add propTypes which is an object directly to the component. Add a a key of count The value of this key will be PropTypes.number.isRequired.

```javascript
const LikeButton = ({ count }) => (
  <span className="like-button">
    <i className="fa fa-heart" />
    {count > 0 && (
      <span className="like-count">{count}</span>
    )}
  </span>
);
LikeButton.propTypes = {
  count: PropTypes.number.isRequired
};
```

PropTypes is the package that you installed, number is the property that means that this thing is expected to be a number,and isRequired means that we'll get a warning if we don't pass in account

**PropTypes will help you track down errors if you use a component the wrong way.**

Do the same thing for the ```<ReTweet>``` componenet

For the ```<Time>``` component do 'PropTypes.string.isRequired'

For ```<Author>```you can set the author prop be an object with a certain shape, using 'PropTypes.shape' and we can pass it an object.

In the object, use the same format set the name and handles properties to PropTypes.string.isRequired. and be sure to set ```<.isRequired>``` on the outside if ```<Proptypes.shape()>```

```javascript
Author.propTypes = {
  author: PropTypes.shape({
    name: PropTypes.string.isRequired,
    handle: PropTypes.string.isRequired
  }).isRequired
};
```

Then set Proptypes on text and hash as well.

Set tweet to be an object using PropTypes.object.isRequired.  You can look at the React docs for the full set of PropTypes validators

```javascript
Tweet.propTypes = {
  tweet: PropTypes.object.isRequired
};
```

## Resources
[Typechecking With PropTypes](https://reactjs.org/docs/typechecking-with-proptypes.html)

[prop-types package](https://www.npmjs.com/package/prop-types)
















