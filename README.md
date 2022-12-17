# recastly-redux
This is a project I completed as a student at [hackreactor](http://hackreactor.com). This project was worked on with a pair.




Project set up

Webpack
Webpack is the official bundler for React applications. All React code should be bundled into a single file before being served up to the client. This achieves two aims:

As our codebase grows, it becomes increasingly cumbersome to manually add script tags to all of our source files to the index.html page. Bundling allows us to only add a single script tag, which references the bundled file.
Multiple script tags means multiple requests, and this means more loading time. Serving up one big file rather than dozens of smaller files reduces multiple request cycles. In this sprint, we've given you a pre-built Webpack file. You'll have to install Webpack (using npm install to install from package.json). Since locally installing webpack saves executables into node_modules/.bin, you'll need to run webpack using the npm script we provided for you, npm run build (see npm docs  for more info). Some useful flags to consider adding to this invocation:
-d: runs Webpack in debug mode, which provides useful error messages to help you understand why Webpack isn't able to bundle your files.
-w: this is the 'watch' flag, and sets webpack to rerun its bundling process every time it detects changes in the source files.
You will experience Webpack more in-depth later on in your Hack-Reactor life, but for now, this is as involved as we need to get.

Live reloading server
In this sprint, you should continue to use the Live Server  package to launch a simple development server that automatically refreshes when you make changes to a file. Live Server is included in this sprint as a dependency. After you install all dependencies for this sprint, you can run the Live Server by using the command:

live-server
npm scripts
Last sprint, you were introduced to scripting  in npm. You can continue to use scripting to simplify your life in this sprint, by automating the Webpack process. Consider writing a bundle script, or defining a start script that handles the multiple steps involved with getting your development environment up and running!

Redux Dev Tools
The Redux Devtools  allow you to inspect your state in graphical form, and presents changes to state as they happen. They are a useful tool in a Redux developer's toolbox!

Bare Minimum Requirements
 Make your API key available to the rest of your application from a new file, 'src/config/youtube.js' Webpack won't build until you create this file.
 Check out this article  for a thorough walkthrough of how to implement Redux and Thunk in a React application.
 Take a moment to think about what actions our application will need. Remember that actions are objects that describe changes to the redux state. A good place to start is to think about what ways the user of our site can interact with it.
 Define your action creators in the actions folder. These are functions which should return your action.
 Plan out what your application state will look like. A good place to start is to look at all of the values that are currently stored in state in our React components. In Redux, we will store all of these values in our Redux state.
 For each value we intend to save in the state, we'll need a reducer. We'll define these in the reducers directory.
 Once all of our reducers are written, we need to combine them into a single root reducer using combineReducers. (Check out the documentation for combineReduers here  for more information)
 Pass the root reducer into createStore to define the store object which contains a Redux state.
 Read this article  to learn about the difference between container components and presentational components.
 Code out the containers set up for you in the containers directory. These should use the React-Redux .connect method to connect the actions you wrote out earlier with the event handlers passed into each component.(Check out the documentation for the .connect method here  for more information)
 In the index.js file, import the Provider class from react-redux, and then use it to wrap your <App /> (Check out the documentation for the Provider component here  for more information)
 Swap out the components in App.js for the containers you just created. You shouldn't have to pass any props down to these components, as they will be pulled directly from your store thanks to the Provider and .connect setup we completed earlier.
Make your API call play nicely with Redux using Thunk.
Redux Thunk is a library that allows us to dispatch actions asynchronously. When Thunk is registered as middleware, our actions are able to return not just objects but functions which can do more advanced things (like invoke dispatch themselves!)

 the Redux Thunk module is already installed in this project. However, you'll have to require it in your store.js file.
 You'll have to use the applyMiddleware method from Redux to allow your store to interpret your thunks. This should be done in your invocation of createStore in store.js.
 in actions/search.js, write out a thunk to interact with the YouTube API. Remember that instead of returning an object, we will now be able to return a function!