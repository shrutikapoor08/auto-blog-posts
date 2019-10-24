
In this blog post, we are going to learn about -
1. State management in a React app
1. Traditional approach of managing state
1. Replacing traditional state management with React Hooks

## Part 1: React Hooks - the what, why and how?

### What are hooks?

Hook is a function that lets you access state without using a class component. 
Hooks are a more natural way of thinking about React. Instead of thinking of what lifecycle methods to use, you can now write components thinking of how your data neeeds to be used. 


React hooks were introduced in October 2018 and released in February 2019.
It is now available with React 16.8 and higher. React hooks became hugely popular as soon as it was introduced.

### What makes react hooks so popular? 
1. Cleaner code.
2. No need to use class components to use state.
3. No need to think of how does React lifecycle events but think in terms of application data. 

What I love about hooks is that it lets you use react state even in a functional component which wasn’t possible before react 16.8. Traditionally, if you had a functional component and you wanted to add state to it, you would have to convert it into a class component.

### The 4 golden hooks

#### 1. useState

useState is used to set and update state like `this.state` in a class component.

```
const [state, setState] = useState(initialState); 
```

#### 2. useEffect

useEffect is used to carry out a function that does side effects. Side effects could include things like DOM manipulation, subscriptions and API calls.

``` 
useEffect(() => {
  document.title = 'New Title' 
});

```


#### 3. useReducer

useReducer works similar to how a reducer works in Redux. useReducer is used when state is more complex. You can actually use useReducer for everything you do with useState. 

```
const [state, dispatch] = useReducer(reducer, initialArg, init);
```

#### 4. useContext
useContext is similar to Context API. In context API, there is a provider method and consumer method. Similarly, with useContext, the closest provider method is used to read data.

```
const value = useContext(MyContext);
```
For more detailed explanation of how each of these work, read [the official docs](https://reactjs.org/docs/hooks-reference.html#usestate)


## Part 2 How to use hooks for state management?

With React 16.8, you can use Hooks out of the box.

We are going to build an application to make a list of songs. Here is what it will do - 

1. Fetch an API for a list of a songs and render it on the UI. 
2. Have an ability to add a song to the list. 
3. When the song gets added to the list, update the list on the frontend and store data on the backend. 

Btw, all the code is available on [my github](https://github.com/shrutikapoor08/hooks-graphql). To see this in action, you can go to [this codesandbox](https://codesandbox.io/embed/github/shrutikapoor08/hooks-graphql/tree/master/)

We are going to use GraphQL with this app. Here are the steps we will do to setup state management using hooks - 

##### Step 1. Setup context.


```
import { createContext } from 'react';

const Context = createContext({
  songs: []
});
```

##### Step 2. Initialize your state. Call this `initialState`

We are going to use this context from to intialize our state
```
 const initialState = useContext(Context);   
```

##### Step 3. Setup reducers using `useReducer`

  Now we are going to setup reducers an initialState with `useReducer` in App.js

```    
   const [state,dispatch] = useReducer(reducer, initialState);
```

##### Step 4. Figure out which is the top level component. 
We will need to setup a Context Provider here. For our example, it will be `App.js`. Also, pass in the dispatch returned from useReducer here so that children can have access to dispatch
``` 
  <Context.Provider value={{state,dispatch}}>
    // children components
  <Context.Provider value={{state,dispatch}}>
```


##### Step 5. Now hook up APIs using `useEffect` hook
```
  const {state, dispatch} = useContext(Context);

  useEffect(() => {
      if(songs) {
          dispatch({type: "ADD_CONTENT", payload: songs});
      }
  }, [songs]);
```

##### Step 6. Update state
You can use `useContext` and `useReducer` to receive and update global application state. For local state like form components, you can use `useState`.

```
  const [artist, setArtist] = useState("");
  const [lyrics, setLyrics] = useState("");
```

And that's it! State management is now set up. 
