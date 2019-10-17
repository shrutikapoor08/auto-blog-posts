
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
3. No need to think of how React lifecycle but think of application data. 

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
  // effectful code
});

```


#### 3. useReducer

useReducer works similar to how a reducer works in Redux if you are familiar with it. useReducer is used when state is more complex.

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

Example 1: Simple counter

Example 2: Slightly advanced

Example 3: Rocket science