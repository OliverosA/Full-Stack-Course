# 1. React Santa Wish List / Santa wish list form in ReactJS

**Kata Link:** https://www.codewars.com/kata/5a9ecd89fd5777e0790001ea

**Description:** Santa wants to simplify his life and offer children the possiblity to enter their wishlist via an online form.

The form should be a React component and should contain:

* An input field for the child's name (with id 'name')
* text area to describe the wish (id: 'wish')
* a drop-down indicating the priority of the wish, from 1 to 5 - default is 1 (id: 'priority')
* the keys in the state to store the corresponding values should be named the same as the element's id
* an onSubmit action calling the function handleSubmit
* a function called handleSubmit, which
  - calls send (a function that is already provided as part of the injected properties props)
  - passes the current state as a parameter to send
  - calls event.preventDefault
* it should be a controlled component (i.e. using onChange to bind input to the component's state)

## `Solution #1`

```JavaScript
const React = require('react');

class WishlistForm extends React.Component {
  constructor(props) {
    super(props);

    this.state = {
      name: '',
      wish: '',
      priority: 1,
    };

    this.handleNameInput = this.handleNameInput.bind(this);
    this.handleWishInput = this.handleWishInput.bind(this);
    this.handlePriorityInput = this.handlePriorityInput.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleNameInput(event) {
    this.setState({
      name: event.target.value,
    });
  }

  handleWishInput(event) {
    this.setState({
      wish: event.target.value,
    });
  }

  handlePriorityInput(event) {
    this.setState({
      priority: event.target.value,
    });
  }

  handleSubmit(event) {
    event.preventDefault();
    this.props.send(this.state);
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input
            id='name'
            type='text'
            value={this.state.name}
            onChange={this.handleNameInput}
          />
        </label>
        <label>
          Wish:
          <textarea
            id='wish'
            value={this.state.wish}
            onChange={this.handleWishInput}
          />
        </label>
        <label>
          Priority
          <select
            id='priority'
            value={this.state.priority}
            onChange={this.handlePriorityInput}
          >
            <option value={1}>1</option>
            <option value={2}>2</option>
            <option value={3}>3</option>
            <option value={4}>4</option>
            <option value={5}>5</option>
          </select>
        </label>
        <input type='submit' value='Submit' />
      </form>
    );
  }
}
```

## `Solution #2`
```JavaScript
const React = require('react');

//using an array of prioritys

const priorityList = [1, 2, 3, 4, 5];

class WishlistForm extends React.Component {
  constructor(props) {
    super(props);

    this.state = {
      name: '',
      wish: '',
      priority: 1,
    };

    this.handleNameInput = this.handleNameInput.bind(this);
    this.handleWishInput = this.handleWishInput.bind(this);
    this.handlePriorityInput = this.handlePriorityInput.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleNameInput(event) {
    this.setState({
      name: event.target.value,
    });
  }

  handleWishInput(event) {
    this.setState({
      wish: event.target.value,
    });
  }

  handlePriorityInput(event) {
    this.setState({
      priority: event.target.value,
    });
  }

  handleSubmit(event) {
    event.preventDefault();
    this.props.send(this.state);
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input
            id='name'
            type='text'
            value={this.state.name}
            onChange={this.handleNameInput}
          />
        </label>
        <label>
          Wish:
          <textarea
            id='wish'
            value={this.state.wish}
            onChange={this.handleWishInput}
          />
        </label>
        <label>
          Priority
          <select
            id='priority'
            value={this.state.priority}
            onChange={this.handlePriorityInput}
          >
            {/*Using map to get array values*/}
            {priorityList.map((value) => (
              <option value={value} id={value} key={value}>
                {value}
              </option>
            ))}
          </select>
        </label>
        <input type='submit' value='Submit' />
      </form>
    );
  }
}
```

# 2. (EXTRA KATA INSIDE) Control the Beast (controlled components in ReactJS)

**Kata Link:** https://www.codewars.com/kata/control-the-beast-controlled-components-in-reactjs

**Description:** In this kata you'll learn how to control Components with different kinds of beasts. Your goal is to tame and control a beast by building a controlled React component with the following criteria:

* Create a component called Beast and its state name
* The beast to control can be passed as a prop name
* Render a textinput field with the id controlledName. Its value should be the name of the current beast.
* Whenever this field's value is modified, the state should be updated as well
* You should control the beast Yeti if name is not passed in

## `My Solution`
```JavaScript
const React = require("react");

class Beast extends React.Component {
  constructor (props) {
    super(props);
    
    this.state = {
      name: props.name
    };
    
  }
  
  
  render() {
    return (
      <input 
        type='text'
        id='controlledName'
        value={this.state.name}
        onChange={ e => this.setState({ name: e.target.value}) }
      />
    );
  }
}

Beast.defaultProps = {
  name: "Yeti"
};
```
