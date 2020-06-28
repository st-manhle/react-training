#Day 3
---
## Style
1. Inline style
```
const pStyle = {
  fontSize: '15px',
  textAlign: 'center',
};

<p style={pStyle}>Hello</p>
```
2. Css Style sheet
- Style.css
```
.DottedBox {
  margin: 40px;
  border: 5px dotted pink;
}

.DottedBox_content {
  font-size: 15px;
  text-align: center;
}
```
- DottedBox.tsx
```
import React from 'react';
import './DottedBox.css';

const DottedBox = () => (
  return (
    <div className="DottedBox">
      <p className="DottedBox_content">Get started with CSS styling</p>
    </div>
  )
);
```
3. Css Module
- Button.module.css
```
.error {
  background-color: red;
}
```
- Button.tsx
```
import React, { Component } from 'react';
import styles from './Button.module.css'; // Import css modules stylesheet as styles
const Button = () => {
  return <button className={styles.error}>Error Button</button>;
}
```
## State
1. What is the state?
- React components has a built-in state object. The state object is where you store property values that belongs to the component. When the state object changes, the component re-renders.

2. What is useState?
- useState is a Hook that lets you add React state to function components.

## Props
1. What is props?
- Props get passed to the component (similar to function parameters)
```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="Sara" />;
```
- Props should not change: Since props are passed in, and they cannot change, you can think of any React component that only uses props as “pure,” that is, it will always render the same output given the same input. This makes them really easy to test.

## Two way binding

```
export default function Test() {
  const [state, setState] = React.useState<string>('');
  function handleChangeName(e) {
    setState(e.target.value);
  }
  return (
    <div>
      <p>My name is {state}</p>
      <input onChange={(e) => handleChangeName(e)}/>
    </div>
  )
}
```
