---
published: false
title: "Managing state with react hooks"
cover_image: "https://raw.githubusercontent.com/maxime1992/my-dev.to/master/blog-posts/manage-dev-to-blog-posts-with-continuous-deployment/assets/github-travis-dev-to.png"
description:
tags: devto, publication, blogpost, continuousdeployment, github, travis
series:
canonical_url:
---

In this blog post, we are going to learn about -
State management in a React app
Traditional approach of managing state
Replacing traditional state management with React Hooks

I have hooked up the application with GraphQL, but it works the same way for REST APIs as well.

## Part 1: React Hooks - the what, why and how?

### What are hooks?

React hooks were introduced in October 2018 and released in February 2019.
It is now available with React 16.8 and higher. React hooks became hugely popular as soon as it was introduced.

What makes react hooks so popular? The main selling point of react hooks is that it lets you use react state even in a functional component which wasn’t possible before react 16.8. Traditionally, if you had a functional component and you wanted to add state to it, you would have to convert it into a class component.

The 4 golden hooks

1. useState

```
const [state, setState] = useState(initialState); 
```
useState is used to set and update state like this.state in a class component.

2. useEffect
``` 
useEffect(() => {
  // effectful code
});

```

useEffect is used to carry out a function that does side effects. Side effects could include things like DOM manipulation, subscriptions and API calls.

3. useReducer

```
const [state, dispatch] = useReducer(reducer, initialArg, init);
```

4. useContext

```
const value = useContext(MyContext);
```

### How to use hooks?

With React 16.8, you can use Hooks out of the box.

Example 1: Simple counter

Example 2: Slightly advanced

Example 3: Rocket science

## Part 2: Adding GraphQL

GraphQL + Hooks


blah blah blah

# TEST
