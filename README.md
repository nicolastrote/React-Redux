# Tuto_React_Redox
Main line on react-redox tutorial

# React

## Installation for Windows

- Enable Dark Mode for Windows 10 Settings and Apps
  - Settings > Personalization > Colors. 
  - Scroll down and select “Dark” under “Choose your app mode”.
 - Enaqble Dark Mode theme in Chrome:
  - morpheon theme: https://chrome.google.com/webstore/detail/morpheon-dark/mafbdhjdkjnoafhfelkjpchpaepjknad?hl=en
 - Darth theme windows: https://github.com/riverar/uxstyle/releases/download/0.2.4.2/UxStyle_0242_x86_x64_preview.exe

- visualstudio : https://code.visualstudio.com/docs/?dv=win  MS code editor
- atom : https://atom.io/     google code editor
  - Babel grammar: 
      - go on Packages > Settings View > Install Packages/Themes >
      - search language-babel (and install it)
      - search atom-formatter-jsbeautify (and install it)
      - search Indent Guide Improved (and install it)
- Google Chrome:
      - Download the React DevTools for a better development experience: https://fb.me/react-devtools
      - (hangout,gmail,)
- git: https://git-for-windows.github.io/
- Node.js: https://nodejs.org/en/download/   npm fait partie de l'environnement
- pour le clavier Francais(Canadien QWERTY avec accolades au dessus du shift droite: )
parametres » langues  »  parametre de region 
» ajouter une region » FRANCAIS (CANADA) puis option et choisir  FRANCAIS (CANADA) 
                                           nb: ! ne pas prendre  FRANCAIS (CANADA) herite
## Clone ReduxCasts Rep from StephenGrider

- cd /Documents/
- git clone https://github.com/StephenGrider/ReduxSimpleStarter    with git Terminal
- cd ReduxSimpleStarter
- npm install     with Nods.js terminal
  all information of this install are in the package.json file
- npm start   for having a web server
and go to http://localhost:8080/

## Code Editing

- open directory with atom and read index.html:
    bundle.js: compile javascript for emtire web site

React : is javascript labrairy for produce html code, with components and views
components: snippet of code that produce HTML
JSX: allow to write HTML code inside JS, but it can t be executed by the browser

test de http://babeljs.io/ : translate "next-gen JavaScript"  TO  "browser-compatible JavaScript"

## Hello world
<i>file index.html</i>
```
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="/style/style.css">
    <link rel="stylesheet" href="https://cdn.rawgit.com/twbs/bootstrap/48938155eb24b4ccdde09426066869504c6dab3c/dist/css/bootstrap.min.css">
  </head>
  <body>
    <div class="container"></div>
  </body>
  <script src="/bundle.js"></script>
</html>
```
<i>file: /src/index.js</i>
```
import React from 'react';
import ReactDom from 'react-dom';
//create new component. This component should produce some html
const App = function() {
  return <div>Hi!</div>;
}
```
//Take this components s generated HTML and put it on the page (in the DOM)
ReactDom.render(<App />, document.querySelector('.container'));

## Coding Notes from React
```
const App = function(){...}   <=>  const App = () => {...}
```
## API Youtube
<i>For Youtube video browser</i>
- https://console.developers.google.com
- create a nube project
- enable the  Youtube Data API V3
- create "credential" (certificat)
- Web Browser (JS)   / Public    code:AIzaSyAQDaKFEtjbyhl6KFXXTWign_bh6p53eIs
<i>For Youtube search taskbar</i>
- open node.js terminal
-$ npm install youtube-api-search

## Function and Class
Always begin with a function, and when you need to add methode (functionnalities) refactor to a class
<table>
  <tr>
    <td>Function<td>
    <td>Class<td>
  <tr>
  <tr>
    <td>
      <p>import React, { Component } from 'react';</p>
      <p>const SearchBar = () => {</p>
      <p>    return <input />;</p>
      <p>}</p>
      <p>export default SearchBar;</p>
    <td>
    <td>
      <p>import React, { Component } from 'react';</p>
      <p>class SearchBar extends Component {</p>
      <p>  render() {</p>
      <p>    return <input />;</p>
      <p>  }</p>
      <p>}</p>
      <p>export default SearchBar;</p>
    <td>
  <tr>
</table>

## Event
```
import React, { Component } from 'react';
class SearchBar extends Component {
  render() {
    return <input onChange={this.onInputChange} />;
  }
  onInputChange(event) {
     console.log(event.target.value);     // that's visible in Chrome Dev. Tool > Console
     // for having all events in console:  console.log(event);
  }
}
export default SearchBar;
```
after refactoring:
```
import React, { Component } from 'react';
class SearchBar extends Component {
  render() {
    return <input onChange={(event) => console.log(event.target.value)} />;
  }
}
export default SearchBar;
```
## State
- plain javascript object that is used to record and react to user events each class based component that we define has its own state object whenever a component state is changed the component immediately renders and also forces all of its children to render as well.
- <b>state is a plain javascript object that exists on any component that's a class based component</b>
- Each instance of a class based component has its own copy of states
- STATE in class MUST BE INITIALISE in constructor
- Each class has its own state object. If component state change all chidren components and it-self are re-render
- exp: state of searchbar change => its children are re-render
- Always update the state with SETSTATE

## Controlled Components

- A controlled component need a "value" attribute. 
- Here the value is initialize with term (empty string at first), 
- and next the event onChange will assign a new string to "value".

```
import React, { Component } from 'react';
class SearchBar extends Component {
  constructor(props) {
      super(props);
      this.state = { term: '' };
  }
  render() {
    return (
      <div>
        <input
            value={this.state.term} // controlled components
            onChange={event => this.setState({ term: event.target.value })} />
      </div>
    )
  }
}
export default SearchBar;
```

# Redox
Redux is a predictable state container for JavaScript apps 
- http://redux.js.org/

React is the view (ie. MVC) and Redoc is the Content of the application.
expl: {List View, items, detail,..}     {List of books, Currently selected books,..}










