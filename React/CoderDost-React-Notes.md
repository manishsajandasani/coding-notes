# Assignments

- **Chapter 1**
  - If we delete `node_modules`. How to run our app again successfully ?
    - cmd: `npm install`
  - How to remove double `console.logs` from React ?
    - Link: `https://bobbyhadz.com/blog/react-why-is-console-log-printed-twice#:~:text=React%20prints%20your%20console.,to%20remove%20the%20StrictMode%20wrapper.`
  - Create a Page with multiple React Apps. Both React Apps should be independent of each other.
  - Try to build a react app using other toolchains like `Vite`

# Why React?

- Single Page Applications.
- Part of Multi-Pages App (MPA)

# What is React?

- React is a free and open-source front-end JavaScript library for building user interfaces based on components.

# What is Component?

- Components are independent and reusable bits of code.
- They serve the same purpose as JavaScript functions, but work in isolation and return HTML.
- Components come in two types, Class components and Function components.

# What is DOM?

- ToDo...

# Setup

- Node.js
  - Download and Install Node.js
  - cmd: `node -v`
  - cmd: `npm -v`
- Create React Application with `create-react-app`
  - cmd: `npx create-react-app my-app`
  - cmd: `npm start` (runs `start script` of `package.json` file)
  - Delete unnecessary files from `public` folder
  - Delete unnecessary files and code from `src` folder
  - When you run `npm start`, it all starts with a file called `index.js` in the `src` folder
  - Use of React Expression `{....}` with Variables
  - Use of JSX
  - Two Components in a Single file. Use the second one in the first one and export only the first one
- Create React Application with `vite`
- Chrome
  - Install `React Developer Tools` Plugin
- VS Code

# Functional Components

- Components are functions that return UI.
- Doesn't matter you give all lowercase letters while exporting the component but it is mandatory to give first letter in uppercase while importing the component.
- Using `export default` enable us to change the component's name while importing the component somewhere else.
- Component's name is replaced by its code wherever the component is invoked.
- Put parentheses after return keyword `return ()` and put all the content inside it. Also helpful while returning multiple lines of code.
- Remember if you wish to return multiple lines of code, then wrap your content inside a `<div>...</div>` or angle brackets `<>...</>` as you can return a single statement only.

```js
==> App.js file
function app() {
  return <div>Hello</div>;
}
export default app;

==> index.js file
import App from "./App";
<App />;
```

# Rules of JSX

- Don't write a component's name as a function but as a tag name. Ex. `App() vs. <App />`
- Don't use lowercase letters for component's name. Ex. `<app /> vs. <App />`
- Wrap your code with a parent tag and it's a must. You can use fragment for this
- In JSX have to end all tags properly. Closing tags are mandatory
- Have to end `img` tag with a `forward slash` else it would generate an error. Ex `<img src="..." alt="..." />`
- Don't use `class` keyword, use `className` keyword in JSX
- For style have to give double `{{  }}` curly braces. Inner one refers to the CSS Object. There is no concept of double curly braces in JSX just like Angular
- Use camel-case for styles. Ex. `font-weight vs. fontWeight`
- You can use props directly but it's highly recommended to destructure them first and then use them in the component
- In case of destructuring Props, we can pass default value(s) also.

```js
<Component name="x" age={42} />;
function Component(name, age) {}
function Component(name = "John Doe", age = 30) {}
```

- Components can be nested so in order to access children, we use `children prop`

```js
<Component>
  <Demo /> (Here Demo is a Child)
</Component>;

function Component({ children }) {
  return <div>{children}</div>;
}
```

# Fragment in React

- It's a rule of JSX to have a common parent of your code
- When you don't have any parent, you can use fragment as the parent tag to wrap your code

```js
<>
  <div className="app-title">App Component</div>
  <Video></Video>
</>
```

# Props

- As the `Attributes` are to `HTML Tags` the same way `Props` are to `Components`
- Props are in the Object Form
- It's highly recommended to destructure Props properties or methods and then use
- Props are read-only in nature. You can't use events to change the value of a Prop
-
