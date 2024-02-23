# ![Installation - React Router](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to install React Router

## Description

React Router is a third party package that plugs into React.  Let's install it

```bash
npm install react-router-dom
```

Now at the top of `src/main.jsx` require it:

```js
import { BrowserRouter } from "react-router-dom";
```

and in the same file (`src/main.jsx`) surround the `<App />` component like so:

```jsx
<BrowserRouter>
	<App />
</BrowserRouter>
```

Congrats!  React Router is now installed and ready to be implemented in your app.