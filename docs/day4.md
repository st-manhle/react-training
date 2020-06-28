#Day 4
---

## Children Props
```
function FancyBorder(props) {
  return (
    <div className={'FancyBorder FancyBorder-' + props.color}>
      {props.children}
    </div>
  );
}

function WelcomeDialog() {
  return (
    <FancyBorder color="blue">
      <h1 className="Dialog-title">
        Welcome
      </h1>
      <p className="Dialog-message">
        Thank you for visiting our spacecraft!
      </p>
    </FancyBorder>
  );
}
```
- Look at the above example, {props.children} is all tag inside FancyBorder Component.
- FancyBorder component will be rendered like:
```
<div className="FancyBorder FancyBorder-blue">
  <h1 className="Dialog-title">
    Welcome
  </h1>
  <p className="Dialog-message">
    Thank you for visiting our spacecraft!
  </p>
</div>
```

## Difference between props and state
| State      | Props |
| ----------- | ----------- |
| Declared and used within Component | Passed from parent component |
| Mutable | Immutable |
| Change inside component | Change by parent component |

## Life cycle of component
1. Class Component  
**componentDidMount()**
 - componentDidMount() Is invoked immediately after a component is mounted
 - Initialization that requires DOM nodes should go here. If you need to load data from a remote endpoint, this is a good place to instantiate the network request.  
**componentDidUpdate()**
 - componentDidUpdate() is invoked immediately after updating occurs. This method is not called for the initial render.
 - Check condition before update inside componentDidUpdate()
**componentWillUnmount()**
 - componentWillUnmount() is invoked immediately before a component is unmounted and destroyed. Perform any necessary cleanup in this method, such as invalidating timers, canceling network requests, or cleaning up any subscriptions that were created in componentDidMount().
2. Function Component
 - Use useEffect to handle hook in function component
```
useEffect(function, [arrayDependencies]);
```
*Note:*  
 *- When you push variable inside arrayDependencies, useEffect function will watch that variable. If the variable inside arrayDependencies changed, useEffect function will re-run*  
 *- When arrayDependencies = [], useEffect function will be run once after view init*  
 *- When useEffect not have arrayDependencies, useEffect function will be run any time after state changed*  

**componentDidMount()**
```
React.useEffect(() => {
  // Do something after view init
}, []);
```
**componentDidUpdate()**
```
const [count, setCount] = React.useState<number>(0);

// Run after count change value
React.useEffect(() => {
  console.log('Count changed');
}, [count])

function handleChangeCount() {
  setCount(count + 1);
}

return (
  <button onClick={() => handleChangeCount}>Add count</button>
);
```

```
React.useEffect(() => {
  // Run after any state is changed
});
```

**componentWillUnmount()**

```
React.useEffect(() => {
  // componentDidMount()
  console.log('Run after view init');
  return () => {
    // componentWillUnmount()
    console.log('Run after component is destroyed');
  }
}, []);
```

