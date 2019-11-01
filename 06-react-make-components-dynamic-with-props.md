# 06. Make Components Dynamic with Props

[Video Link](https://egghead.io/lessons/react-make-components-dynamic-with-props)

You're going to replace hard-coded data  with dynamic values that are called props in React.


Dave pasted in a data object with all the tweet details.

Inside of ReactDOM.render pass in tweet as props to the Tweet component. Use curly braces to pass in the props of tweet as data.

```javascript```
ReactDOM.render(
    <Tweet tweet={data}/>,
    document.querySelector('#root')
);
```
Now your Tweet component can receive the props. Every prop will be object of this object.

```javascript
function Tweet(props) {
    return ();
}
```

Then pass the ```<message>``` prop down to the ```<message>``` component.

```javascript
<Message text={props.tweet.message}/>
```
You can also destucture the props object and pull out tweet. Then pass in just ```<tweet.message>``` 

```javascript
function Tweet(props){
const { tweet } = props;
return (...
    <Message text={tweet.message}/>
    )
}
```
**It's more common to do the destructuring in the argument of the React component.**

```javascript
fucntion Tweet({ tweet }) {
return (...
     <Message text={tweet.message}/>
    )
}
```

You repeat those steps to pass in props for the ```<Message>```, ```<Author>```, and ```<Handle>``` components.

For the time component we need to install the time libray moment once it's installed we need to import moment from momment.

**You pass in individual properties from the tweet instead of whole tweet to make your component resusale.**

Go into time use the moment library to display the time using moment pass in time and ```<.fromNow()>```.

```javascript
const Time = ({ time }) => (
    <span className="time">
    {moment(time).fromNow()}
    </span>
)
```
The last two components take in a count prop. 

In ```<LikeButton>``` add a span and put count inside of it.

```javascript
<span className="like-button">
    <i className="fa fa-heart" />
    //add this span
    <span className="like-count">{count}</span>
</span>
```

In our ```<LikeButton>``` component tag a we'll add count and tweet.likes.

```javascript
<LikeButton count={tweet.likes}>
```
Going back to the ```<LikeButton>``` 
component make it only render it if the like count is more than 0.

```javascript
<span className="like-button">
    <i className="fa fa-heart" />
//add count    {count > 0 && <span className="like-count">{count}</span>
</span>
```
You can use another way to get dynamic content for the ```<RetweetButtton>``` component. 

Make a new function called ```<getRetweetCount>``` pass in count as the arguments. You now can write JavaScript and create and if statement that read if count is greater than 0 then return span. If not return null.

```javascript
function getRetweetButton(count) {
    if(count > 0) {
        return <span className="retweet-count">{count}</span>
    }
    return null;
}
```
Then inside of the ```<RetweetButton>``` component you'll add in a function call to the ```{getRetweetCount(count)}```

```javascript
const RetweetButton = ({ count }) => (
    <span className="retweet-button">
    <i className="fa fa-retweet" />
    {getRetweetCount(count)}
    </span>
);
```
Lastly, we'll go to the ```<RetweetButton>``` and count equal to tweet.retweets.

```javascript
<RetweetButton count={tweet.retweets}>
```

## Resources
[Components and Props React Docs](https://reactjs.org/docs/components-and-props.html)

[Moment.js](https://momentjs.com/)






