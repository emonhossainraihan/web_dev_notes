In this project we will learn how to work with redux in react based project:

- **React Redux pattern** : Action Creators, reducers, provide the store and connect the components. Components can access state ans dispatch actions.

## Contents

- [File-Structure](#file-structure)
- [Action](#action)
- [Reducer](#reducer)
- [Store](#store)
- [Subscribe](#subscribe)

## File-Structure

![](/images/01.png)

## Action

Actions are payloads of information that send data from your application to your store. They are the only source of information for the store. You send them to the store using `store.dispatch()`.

![](/images/02.png)
![](/images/03.png)

## Reducer

A reducer is a function that determines changes to an application’s state. It uses the action it receives to determine this change.
The reducer is a pure function that takes the previous state and an action, and returns the next state. Update data immutably(don't modify inputs)

```js
const contactReducer = (state = initialState, action) => {
  // Do something
};
```

State changes are based on a user’s interaction, or even something like a network request. If the application’s state is managed by Redux, the changes happen inside a reducer function — this is the only place where state changes happen. The reducer function makes use of the initial state of the application and something called action, to determine what the new state will look like. The state is meant to be immutable, meaning it shouldn’t be changed directly. To create an updated state, we can make use of `Object.assign` or opt for the `spread operator`. Earlier, we noted that the update that happens depends on the value of `action.type`. The switch statement conditionally determines the kind of update we're dealing with, based on the value of the `action.type`.

![](/images/04.png)
![](/images/05.png)

## Store

A [store](https://redux.js.org/api/store/) holds the whole state tree of your application. The only way to change the state inside it is to dispatch an action on it. A store is not a class. It's just an object with a few methods on it. To create it, pass your root reducing function to `createStore`.

**Store Methods**

- getState()
- dispatch(action)
- subscribe(listener)
- replaceReducer(nextReducer)

![](/images/06.png)
![](/images/07.png)
![](/images/08.png)

## Subscribe

Ok you provide the global store to each and every component but if any component need any piece of data from the global state it should go through by subscribing the global store and get the state via `mapStateToProps`. And if it need to pass any information of new data to the global store then it should trigger an action which come from `mapDispatchToProps`.

![](/images/09.png)
![](/images/10.png)

<hr>

All you see just triggering synchronous action what if you need to fetch data inside your action to pass data as payload to the reducers? Here come redux-thunk middleware

> _Redux Thunk teaches Redux to recognize special kinds of actions that are in fact functions_

When an action creator returns a function, that function will get executed by the Redux Thunk middleware. This function doesn't need to be pure; it is thus allowed to have side effects, including executing asynchronous API calls. The function can also dispatch actions. The thunk can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met.

If Redux Thunk middleware is enabled, any time you attempt to dispatch a function instead of an action object, the middleware will call that function with dispatch method itself as the first argument.

And then since we “taught” Redux to recognize such “special” action creators (we call them thunk action creators), we can now use them in any place where we would use regular action creators.

This was the motivation for **finding a way to “legitimize” this pattern of providing dispatch to a helper function, and help Redux “see” such asynchronous action creators as a special case of normal action creators** rather than totally different functions.
