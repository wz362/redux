# Tech Stack

Display tech stacks via Redux.

### Set up
Install dependencies:
```sh
npm install --save redux react-redux
```


### Running

Run project:
```sh
cd redux
react-native run-ios
```

### Notes

Action: an object that tells the reducer how to change its data

Reducer: a function that returns some data

State: data for our app to use

Store: an object that holds the application's app = Reducer + State

```sh
const reducer = (state = [], action) => {
  if (action.type === 'split_string') {
    return action.payload.split('');
  } else if (action.type === 'add_character') {
    return [ ...state, action.payload ];
  }
  
  return state;
};

const store = Redux.createStore(reducer);

store.getState();

const action = { 
  type: 'split_string', 
  payload: 'asdf' 
}; // plain JS object

store.dispatch(action);

store.getState();

const action2 = {
  type: 'add_character',
  payload: 'a'
}

store.dispatch(action2);
store.getState();
```