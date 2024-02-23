# ![React Router - Creating Routes](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create routes that will display different components based on the URL in the browser

## Description

In this section, we're going to set up React Router to display different components, based on the URL that we type into the URL bar in the browser.

## Add Your First Route

At the top of `src/App.jsx`, let's import the following:

```js
import { Routes, Route } from "react-router-dom";
```

Now adjust the `return` statement so it matches this:

```jsx
return (
	<>
		<h1>Pokemon!</h1>
		<Routes>
			<Route path="/pokemon" element={<Pokemon/>} />
		</Routes>
	</>
);
```

- The `<Routes>` component will contain all of the individual routes for our application
- The `<Route>` component defines a single route based on the props it is passed
	- When the path section of the URL in the browser matches the value set to `path` (in this case `/pokemon`, it will display the component that `element` is set to (in this case `<Pokemon/>`)

Now if you go to `http://localhost:5173/` you'll just see the header `Pokemon!`.

If you change the URL to `http://localhost:5173/pokemon` the `<Pokemon/>` component will be displayed as well.

## Create a Root Route

Let's create a route for the URL `http://localhost:5173/`.  In `App.jsx`, create the following component just above the `const Pokemon` component declaration.

```jsx
const Home = () => {
	return (
		<>
			<h2>Home</h2>
			<p>Welcome to my Pokemon website!</p>
		</>
	);
}
```

Now let's add a route for displaying that component by updating your `<Routes>` component like so:

```jsx
<Routes>
	<Route path="/" element={<Home />} />
	<Route path="/pokemon" element={<Pokemon/>} />
</Routes>
```

Now alter the path in your URL from `http://localhost:5173/` to `http://localhost:5173/pokemon` and back.  You should notice the relevant component is displayed, depending on whether the path is `/` or `/pokemon`