---
title: React + Redux 
author:
  name: Team141
  link: https://github.com/Team141
date: 2023-05-22 16:30:00 +0530
categories: [React, Redux]
tags: [React, Redux]
math: true
mermaid: true
pin: false
---

## Sample React & Redux Application

---

### Sample *React & Redux* working application

```javascript
const { createStore, bindActionCreators } = Redux;
const { Provider, connect } = ReactRedux;

//REDUX:
const ADD='ADD';

const addMessage =(message)=>{
  return {
  type:ADD,
  message
  };
}

const messageReducer = (state=[], action)=>{
  switch(action.type){
    case ADD:
      return state.concat(action.message);
      break;
    default:
      return state;
  }
}

const store = Redux.createStore(messageReducer);

//REACT:

class DisplayMessages extends React.Component {
  constructor(props){
    super(props);
    
    this.state={
      input:'',
    };
  }
  
  handleChange(event){
    this.setState({
      input: event.target.value
    })
  };
  
  submitMessage(){
    this.props.submitNewMessage(this.state.input);
    this.setState((state)=>{
      return{
      input:'',
    };
    });
  }
  
  render(){
    return (
    <div>
      <input onChange={this.handleChange.bind(this)} value={this.state.input}/>
        <button onClick={this.submitMessage.bind(this)}>Submit</button>
        <ul>
          {this.props.messages.map((messages,idx)=>{
            return(
              <li key={idx}>{messages}</li>
            )
          })}
        </ul>
    </div>
    );
  } 
}


//REACT-REDUX CONNECT:
const mapStateToProps = (state) =>{
  return {
    messages: state
  }
}

const mapDispatchToProps = (dispatch)=>{
  return {
    submitNewMessage:(newMessage)=>{
      dispatch(addMessage(newMessage))
    }
  }
}

const Container = connect(mapStateToProps,mapDispatchToProps)(DisplayMessages)

//Provider:
class AddWrapper extends React.Component{
  render(){
  return(
    <Provider store={store}>
    <Container/>
    </Provider>
  );
  }
}


ReactDOM.render(<AddWrapper/>, document.getElementById('root'))

//HTML:<div id="root"></div>
```
{: .nolineno}

---

### Required Imports for React Application

```javascript
/*
import React from 'react'
import ReactDOM from 'react-dom'
import { Provider, connect } from 'react-redux'
import { createStore, combineReducers, applyMiddleware } from 'redux'
import thunk from 'redux-thunk'

import rootReducer from './redux/reducers'
import App from './components/App'

const store = createStore(
  rootReducer,
  applyMiddleware(thunk)
);

ReactDOM.render(
  <Provider store={store}>
    <App/>
  </Provider>,
  document.getElementById('root')
);
*/

// Only change code below this line
console.log('Now I know React and Redux!')
```
{: .nolineno}

## You can use following links to test above code

Online Testing Environment <https://codepen.io/>

## To test locally set up React in you PC using following Link
<https://www.freecodecamp.org/news/install-react-with-create-react-app/>


