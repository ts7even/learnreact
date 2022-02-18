
# learnreact
Notes to learn react

# How to start a project. 
* npx create-react-app frontend
* cd frontend
* npm start (to start up the development folder)

# Configure SRC folder and Directory 
- Inside of src folder you only need...  (To clean up the project)
* app.js
* index.css
* index.js 

# Inside of app.js
```
function App() {
  return (
    <div>
      <h2>Let's get started!</h2>
    </div>
  );
}
```
export default App;

# Inside of index.js
```
import ReactDOM from 'react-dom';

import './index.css';
import App from './App';

ReactDOM.render(<App />, document.getElementById('root'));
```

# Inside of index.css

```
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Noto Sans JP', sans-serif;
}

body {
  margin: 0;
  background-color: #3f3f3f;
}
```

# Flow of React 
Components -> App.js -> (index.js + index.css) -> index.html : 
- So the user clicks the Html link then processes index.js, then renders App.js, then gets whatever components. 
- For now, dont toutch package.json. You will need to change this later when running a backend. 
```
const ExpenseItem = () => {
  return (
    <div>ExpenseItem</div>
  )
}

export default ExpenseItem
```
# Creating our first custom component
- Add new folder inside of src called components. (This is where you store your components)
* Create a new file called ExpenseItem.js (Must be upper case, since built in characters in HTML are lower case so we dont want problems)
* use rafce to create react arrow function with export. You need to delete the import react at the top because it wont render in App.js if you leave it. 
```

```


* import Expense item to App.js. You can use the function ExpenseItem as a html tag  inside of app.js
```
import ExpenseItem from "./components/ExpenseItem";

function App() {
  return (
    <div>
      <h2>Let's get started!</h2>
      <ExpenseItem></ExpenseItem>
    </div>
  );
}

export default App;
```
# React State Vs Props 


# React Hooks 

