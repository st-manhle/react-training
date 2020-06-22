#Day 2
---
## Creating a Functional Component
- Angular
```
<p>Hello {{name}}</p>
```
- ReactJS
```
<p>Hello {name}</p>
```

## Input/Output
### - Input
- Angular
> parent.component.html
```
<app-child [value]='1'></app-child>
```
> child.component.ts
```
@Input value: number
```
- ReactJS
> parent.tsx
```
<Child value={1} />
```
> child.tsx
```
export default function Child(props) {
  return <div>{props.value}</div>
}
```
### - Output
- Angular
> parent.component.html
```
<app-child (onChange)="handleChange($event)"></app-child>
```
> child.component.ts
```
@Output onChange = new EventEmitter()
```
- ReactJS
> parent.tsx
```
<Child onHandleInputChange={handleChange($event)} /> 
```
> child.tsx
```
export default function Child(props) {
  return <input onChange={props.onHandleInputChange($event)}>{props.value}</div>
}
```

## Conditional and List rendering
### - If
- Angular
```
<div *ngIf="isLoggedIn; else loggedOut">
  <p>Welcome Manh!</p>
</div>

<ng-template #loggedOut>
  <p>Please Login!</p>
</ng-template>
```

- ReactJS

```
return (
  {
    isLoggedIn ? (
      <p>Welcome Manh!</p>
    ) : (
      <p>Please Login!</p>
    )
  }
)
```

### - For
- Angular
```
<li *ngFor="let item of list">
  <p>{{item.name}}</p>
</li>
```

- ReactJS
```
return (
  list.map((item: any) => {
    <p key={item.id}>{item.name}</p>
  })
)
```