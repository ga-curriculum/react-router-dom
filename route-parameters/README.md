# ![React Router DOM - Route Parameters](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to access URL params.

## Description

Up until now, we can only have static paths in our links like `/home` or `/pokemon`.  In this section we're going to add dynamic URL segments so that we can have links like `/pokemon/1` that we'll use to access single elements from the `pokemon` array.

## Create Dynamic Links

Note that the `<Pokemon/>` component displays all of the Pokemon.  We're going to turn the text of each `<li>` into a link.  Update the `return` statement of `<Pokemon />` like so:

```jsx
return <li key={currentPokemon.name}>
	<Link to={"/pokemon/" + index}>
		{currentPokemon.name}
	</Link>
</li>
```

Go back to the browser and hover over the links, checking the status bar at the bottom of the browser.  You'll see that each link is different (e.g. `http://localhost:5173/pokemon/2`, `http://localhost:5173/pokemon/0`, etc.)

## Define a Route That Accepts Dynamic Params

Let's create a route that will match the dynamic links generate in the last section.  Update the `<Routes/>` component of the `<App/>` component like so:

```jsx
<Routes>
	<Route path="/" element={<Home />} />
	<Route path="/pokemon" element={<Pokemon/>} />
	<Route path="/pokemon/:id" element={<SinglePokemon/>} />
</Routes>
```

Now let's import `useParams` from `react-router-dom` which will allow us to access that dynamic `:id` URL param inside components.  Update your `import` statement at the top of `src/App.jsx`:

```js
import { Routes, Route, Link, useParams } from "react-router-dom";
```

And let's create simple `<SinglePokemon/>` component that will just display the `:id` portion of its matching URL:

```jsx
const SinglePokemon = () => {
	const id = useParams().id
	return <>
		{id}
	</>
}
```

`useParams()` returns an object whose properties match the URL params.  Because the `path` prop for the corresponding `<Route/>` is `/pokemon/:id`, there is a property on the object that `useParms()` returns whose key is `id`.  The value of this property will be the value in the 2nd segment of the path section of the URL.  For instance, if the path is `/pokemon/1`, `id` will be `1`.

Test the browser to see that when you click on a Pokemon link, it displays the appropriate "id" (really the index in the `pokemon` array if you examine the `<Pokemon/>` component).  For instance, clicking on "bulbasaur" should display `0`.

Once that works, we can flesh out the `<SinglePokemon/>` component with data from the `pokemon` array:

```jsx
return (
	<>
		<h2>{pokemon[id].name}</h2>
		<dl>
			<dt>Weight:</dt>
			<dd>{pokemon[id].weight}</dd>
			<dt>Height:</dt>
			<dd>{pokemon[id].height}</dd>
		</dl>
	</>
)
```