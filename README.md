# edu-react-intro

> Starta en react applikation utan script, och utan babel.

## Instruktioner

```bash
cd ~
cd ws
mkdir edu-react-intro
cd edu-react-intro
npm init -y
npm pkg set scripts.start="parcel ./src/app/index.html"
mkdir -p ./src/app/components
touch src/app/components/app.tsx
touch ./src/app/index.html
touch ./src/app/index.tsx
touch tsconfig.json
npm i react 
npm i react-dom 
npm i typescript 
npm i -D parcel-bundler
```

## DoD

```bash
npm start
```

## index.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Hello React</title>
  </head>
  <body>
    <div id="mountNode"></div>
    <script type="module" src="./index.tsx"></script>
  </body>
</html>
```


## index.js

```js
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>React App</title>
</head>

<body>
    <div id="app"></div>
</body>

</html>
```

## app.tsx

```tsx
import React, { useState } from 'react';

export default function App() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

## tsconfig.json

```json
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "moduleResolution": "node",
    "esModuleInterop": true,
    "jsx": "react",
    "outDir": "./build",
    "skipLibCheck": true,
    "allowJs": true
  }
}
```
