# 09. Build the GitHub File List app

[Video Link](https://egghead.io/lessons/react-build-the-github-file-list-app)



Open up index.js and create a  ```<FileList>``` component. Pass in some props called files

In the FilesList tag we pass in data as props

```javascript
ReactDOM.render(
    <FileList files={data}/>,
    document.querySelector('root'0)
);
```

Create a table element with the className of file-list. Inside that, have <tbody>. Which is where we'll render the files.

**React doesn't know how to render objects**

Use the bult-in map function. For each file, will render as a JSX element. Which will be a ```<FileListItem>``` component which takes file as a prop.

Also add a prop called key.
**This key needs to be unique for each item in the list**

The key also needs to be consistant Math.random() or using the array index are bad examples for keys.

The best option for a key is going to be the file's ID. If you have an object that has a unique ID, that's the best key to use

```javascript
const FileList = ({ files }) => (
    <table className="file-list">
        <tbody>{file.map(file => (
            <FileListItem file = {file} key={file.id}/>
        ))}</tbody>
        </table>
);
```

Create the ```<FileListItem>``` component it takes file as props. Have it return a TR, with a class of file-list-item.

Inside the ```<tr>``` render ```<FileName/>``` and pass in file. Next create the ```<FileName>``` component, pass it file as well.

```javascript
const FileListItem = ({ file }) => (
    <tr className="file-list-item">
    <FileName file={file}/>
    </tr>
)

const FileName = ({ file }) => <div>{file.name}</div>;
```

**You can't render divs inside trs. This rule comes from HTML**

Table rows can only have table cells in them. ```<FileName>``` is going to have to be a <td> instead of a <tr>.

```javascript
const FileName = ({ file }) => ( <td className="file-name">{file.name}</td>;
)
```

 Create a ```<FileIcon>``` component, pass file as a prop. This will decide which icon to render based on the file name. You can switch on file.type.

 On the switch, if the file type is folder,set icon to fa-folder. This is a Font Awesome icon name. 
 
 Then create a variable called icon and add a break out of this case. If the next case is file will set the icon to 'fa-file-text-o'.

 You also need a default case for this switch. Make file the default icon type. Make the switch return a JSX element. 

Create an I element with a dynamic className.


 ```javascript
const FileIcon = ({ file }) => {
    let icon;
    switch(file.type) {
        case 'folder';
        icon = 'fa-folder'
        break;
    default:
        case 'file';
          icon = 'fa-file-text-o'
    }
    return (
        <i className={`fa ${icon}`}/>
    )
}
 ```

**You can't return more than one item from a component**


To get around this you can use the React fragment syntax, the empty tag. We also put ```<FileIcon>``` in a ```<td>```and give it a class name of file-icon.

```javascript
const FileName = ({ file }) => ( 
    <>
    <td className="file-icon">
        <FileIcon file={file} />
    </td>
    <td className="file-name">{file.name}</td>;
    </>
);
```

Now you need the ```<CommitMessage>``` component. Next to ```<FileName>``` render ```<CommitMessage>```. Pass a commit prop. and pass in file.latestCommit. 

Then create the  ```<CommitMessage>``` component and it will take commit and render out a <td> with a commit-message class and set it to commit.message.

```javascript
const CommitMessage = ({ commit}) => (
    <td className="commit-message">{commit.message}</td>
)
```


The last thing to add is the ```<time>``` component. You can reuse the time component from the tweet example. Open up the console, add the moment library again.

Copy the time.js file form the Tweet example and put it in the source directory.

import Time from time.js it inside of your index.js file 

The ```<Time>``` component renders a span you need a tr. Create a tr  with a className of age inside of ```<FileListItem>``` under ```<CommitMessage>```.Add in Time and pass in time as a prop and pass in file.updated_at

```javascript
const FileListItem = ({ file }) => (
  <tr className="file-list-item">
    <FileName file={file} />
    <CommitMessage commit={file.latestCommit} />
    <td className="age">
      <Time time={file.updated_at} />
    </td>
  </tr>
);
```


## Personal Take:
Was a fan of using a reusable component in this lesson since it was mentioned in the previous lesson.



## Resources
[React Fragment Syntax](https://reactjs.org/docs/fragments.html#short-syntax)









