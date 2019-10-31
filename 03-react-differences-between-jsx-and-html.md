# 01. Differences Between JSX and HTML

[Video Link](https://egghead.io/lessons/react-differences-between-jsx-and-html)

The big difference between JSX and HTML is adding class to an element. Instead of class you would add className.

Using class will work but you will get a warning in the Dev Tools. 

Another thing is event handlers in JSX needs to be camel cased (```<onClick>```, ```<onKeyPress>```, etc). One that is different is ```<ondblclick>``` in JSX it's spelled out ```<onDoubleClick>```.

When you make an input with an ID of email , normally you would write label then for  for property set to email. In React, we need to use ```<htmlFor>``` instead of just for. 

**Every tag need to be closed in JSX**

Make sure you close ```<inputs>``` and  ```<divs>```. In JSX every tag can be self closing. If you want an empty ```<div>``` you don't have to wrtie it out like <div></div>.

Also if you want to add comments in JSX. You can use JavaScript comments so inside of curly braces use /* and
end with */. 

For multiple lines use //. If you use // on a single line the comment will comment out your closing brace.

**The most common mistake is using class instead of className.**

```javascript
{/* comments */}

{
    // Comments
    // Comments
}
```




## Resources
[Introducing JSX React Docs](https://reactjs.org/docs/introducing-jsx.html)


