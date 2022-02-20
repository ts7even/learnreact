# How to start a project. This can be replicated for all React frontend websites. 
* npx create-react-app frontend
* cd frontend
* npm start (to start up the development folder)

# Configure SRC folder and Directory 
- Inside of src folder you only need...  (To clean up the project) Or you can jsut delete the folder and recreate it.
* App.css
* App.js
* index.css
* index.js 

- Then you need to Add a few folders inside of src. 
* Add container foldler ~ This is for larger jsx function such as for a footer, header, blog, and other "Pages"
* Add a components folder ~ These are for smaller jsx functions that can be resused in different pages such as a NavBar. 
* Add a assets folder ~ This is where you keep all of your pictures such as svg's, png, ect...

# Inside of app.js
* Use the rafce shortcut to create this function. 
```
import React from 'react';

function App() {
  return (
    <div>
      <h2>Let's get started!</h2>
    </div>
  );
}

export default App
```


# Inside of index.js
* Just import App.js to the index.js  This does not change throughout the build. 
```
import ReactDOM from 'react-dom';

import App from './App';
import './index.css';

ReactDOM.render(<App />, document.getElementById('root'));
```

# Inside of index.css
* This is where we create varibles for our initial set up that can be used for App.css and other component and containers. 
* Think of this like getting your paint and paint brushes ready for your canvas. 
* The varibles created can be used in other css files like in containers and components. 

```
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@200;300;400;500;600;700;800&display=swap');

:root {
  --font-family: 'Manrope', sans-serif;

  --gradient-text: linear-gradient(89.97deg, #AE67FA 1.84%, #F49867 102.67%);
  --gradient-bar: linear-gradient(103.22deg, #AE67FA -13.86%, #F49867 99.55%);
  
  --color-bg: #040C18;
  --color-footer : #031B34;
  --color-blog: #042c54;
  --color-text: #81AFDD;
  --color-subtext: #FF8A71;
}
```
# App.css
* This is where we frame and style the overall website to fit accordingly. 
* Think of this as cutting a molding our canvas to fit properly between different screens. 
```
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
  scroll-behavior: smooth;
}

body {
  background: var(--color-bg);
}

a {
  color: unset;
  text-decoration: none;
}

.gradient__bg {
  background:-moz-radial-gradient(circle at 3% 25%, rgba(0, 40, 83, 1) 0%, rgba(4, 12, 24, 1) 25%);

  /* safari 5.1+,chrome 10+ */
  background:-webkit-radial-gradient(circle at 3% 25%, rgba(0, 40, 83, 1) 0%, rgba(4, 12, 24, 1) 25%);

  /* opera 11.10+ */
  background:-o-radial-gradient(circle at 3% 25%, rgba(0, 40, 83, 1) 0%, rgba(4, 12, 24, 1) 25%);

  /* ie 10+ */
  background:-ms-radial-gradient(circle at 3% 25%, rgba(0, 40, 83, 1) 0%, rgba(4, 12, 24, 1) 25%);

  /* global 92%+ browsers support */
  background:radial-gradient(circle at 3% 25%, rgba(0, 40, 83, 1) 0%, rgba(4, 12, 24, 1) 25%);
}

.gradient__text {
  background: var(--gradient-text);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.section__padding {
  padding: 4rem 6rem;
}

.section__margin {
  margin: 4rem 6rem;
}

.scale-up-center {
	-webkit-animation: scale-up-center 0.4s cubic-bezier(0.390, 0.575, 0.565, 1.000) both;
	animation: scale-up-center 0.4s cubic-bezier(0.390, 0.575, 0.565, 1.000) both;
}

@-webkit-keyframes scale-up-center {
  0% {
    -webkit-transform: scale(0.5);
            transform: scale(0.5);
  }
  100% {
    -webkit-transform: scale(1);
            transform: scale(1);
  }
}

@keyframes scale-up-center {
  0% {
    -webkit-transform: scale(0.5);
            transform: scale(0.5);
  }
  100% {
    -webkit-transform: scale(1);
            transform: scale(1);
  }
}

@media screen and (max-width: 700px) {
  .section__padding {
    padding: 4rem;
  }

  .section__margin {
    margin: 4rem;
  }
}

@media screen and (max-width: 550px) {
  .section__padding {
    padding: 4rem 2rem;
  }

  .section__margin {
    margin: 4rem 2rem;
  }  
}

```


# Flow of React 
Components -> Containers -> App.js -> index.js -> index.html : (Vice versa when a person goes to the website)
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
* Create a new file called Whatever.js (Must be upper case, since built in characters in HTML are lower case so we dont want problems)
* use rafce to create react arrow function with export. You need to delete the import react at the top because it wont render in App.js if you leave it. 
* Create a css file with same name 
* This can be repeated for compnents and containers. Containers are larger that a comonent, like a whole page. 
* Copy and paste this to other components and conatiners, but alt + left click to change the funciton name, div, and export. 
```
import React from 'react';
import './navbar.css';

const Navbar = () => {
  return (
    <div>Navbar</div>
  )
}

export default Navbar

```


# Export Container and Compenent folders and files. 
* You have to create a index.js file in either containers or components to export all jsx and css files.
```
export {default as Article } from './article/Article';
export {default as Brand } from './brand/Brand';
export {default as CTA } from './cta/CTA';
export {default as Feature } from './feature/Feature';
export {default as Navbar } from './navbar/Navbar';
```

*  You can use the function Compenent JSX files as a html tag inside of app.js

```
import React from 'react';

import {Footer, Blog, Possibility, Features, WhatGPT3, Header} from './containers';
import {CTA, Brand, Article, Feature, Navbar} from './components';


const App = () => {
  return (
    <div className='App'>
      <div className='gradient__bg'>
        <Navbar />
        <Header />
      </div>
      <Brand />
      <WhatGPT3 />
      <Features />
      <Possibility />
      <CTA />
      <Blog />
      <Footer />
    </div>
  )
}

export default App
```






# React Routes
- To add other pages and their routes, you have to import Route from react-router-dom
```
import {Route} from 'react-router-dom';

import {Whatever page.js} from './path to Whateverjs'; 
import {Whatever page.js} from './path to Whateverjs';
import {Whatever page.js} from './path to Whateverjs';


function App() {
  return (
    <div>
      <Route path='/'>
        <Whateverpage.js/>
      </Route>
      <Route path='/'>
        <Whateverpage.js/>
      </Route>
      <Route path='/'>
        <Whateverpage.js/>
      </Route>
    </div>
  );
}


```

# React Hooks,  To be contined...
