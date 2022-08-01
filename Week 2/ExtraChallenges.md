# 1. Easter egg list in ReactJS

**Kata Link:** https://www.codewars.com/kata/5a95947f4a6b342636000173/train/javascript

**Description:** You decide to create a simple list of your favourite Easter eggs in React.

Challenge
Learn about nesting and listing React components.

The component EggList will set a prop called eggs which is an array of your favourite easter eggs e.g. "Lindt".
Loop through the props.eggs to output a unorder list of Easter eggs.
Each list item should be a component called EasterEgg with a prop name, to render the name in a li tag.
Each EasterEgg will need a key prop with a unique id. Use the index of the array for now.

**About keys in React lists**

While you can use the index of the array for a key because they should be unique among their siblings. However it is better to use unique values.

Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity

## `My Solution`
```JavaScript
import React from 'react';

export const EggList = ({eggs}) => { // setting the name to the Easter Egg component
  return <ul>{eggs.map((value, id) => <EasterEgg name={value} key={id}/>)}</ul>;
};

export const EasterEgg = ({name, key}) => {
  return <li key={key}>{name}</li>;
};
```

# 1. PC upgrade specs using HOC in ReactJS

**Kata Link:** https://www.codewars.com/kata/5a9c0fa45084d79b1f000138

**Description:** First steps to learning the basics of higher order components (HOC) in ReactJS

A HOC is a function that takes a component as the first parameter and returns a function wrapping the first parameter.

```JavaScript
function withExample(Component) {
  return function(props) {
    return <Component />
  }
}
```
**Challenge**

You're building a new feature on your e-commerce site which displays two computer specs - basic and pro.
The PcDisplay component is already built and expects 5 props. { title, price, cpu, ram, ssd }
You will need to build a withPriceModel HOC and using that to manage the price of the BasicModel and ProModel components.

* Build a HOC called withPriceModel which takes the PcDisplay component for first param and price increase number for the second param.

* `withPriceModel` will manage the price and must set a default price of 50.

* `BasicModel` should use the default price set by `withPriceModel`

* `ProModel` should use `withPriceModel` to increase the price by 60. Total price should be 110.

* Since the `withPriceModel` is responsible for managing the price, ensure that it can't be overritten by passing in a price prop.

## `My Solution`
```JavaScript
const React = require('react');

// Don't change PcDisplay
const PcDisplay = (props) => {
  return (<div>
  <h1>{props.title}</h1>
  <p id="price">£{props.price}</p>
  <ul>
    <li><label>CPU</label> <span>{props.cpu}</span></li>
    <li><label>RAM</label> <span>{props.ram}</span></li>
    <li><label>SSD</label> <span>{props.ssd}</span></li>
  </ul>
  </div>);
};

// Implement HOC -> returns a functions that wraps the passed in `PcDisplay` component
let withPriceModel = (WrappedComponent, increase = 0) => {
  return (props) => {
    return <WrappedComponent
            title = { props.title }
            price = { 50 + increase }
            cpu = { props.cpu }
            ram = { props.ram }
            ssd = { props.ssd }
            />
  }
};

// Build basic and pro model components using `withPriceModel`
const BasicModel = withPriceModel(PcDisplay);

const ProModel = withPriceModel(PcDisplay, 60);
```
