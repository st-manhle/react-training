#Day 1
---
## Using Create React App
```
npm i -g npx
npx create-react-app my-app --template typescript
cd my-app
npm start
```

## Creating a Functional Component
- Home.tsx
```
import React from 'react';

export default function Home() {
  return (
    <p>Hello World</p>
  )
}
```

## Working with Components & Re-Using Them
- App.tsx
```
import React from 'react';
import Home from '../src/pages/home/Home';

function App() {
  return (
    <Home />
  );
}

export default App;
```
