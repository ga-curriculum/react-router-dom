# ![React Router - Setup](./assets/hero.png)

## Setup

Open your Terminal application and navigate to your **`~/code/ga/lectures`** directory:

```bash
cd ~/code/ga/lectures
```

Create a new Vite project for your React app:

```bash
npm create vite@latest
```

You'll be prompted to provide a project name. `vite-project` is the default, but when you start typing that default will go away. Choose a name that makes sense for this project; in this case, we'll call the app `react-router`.

Select a framework. Use the arrow keys to choose the `React` option and hit `Enter`.

Select a variant. Again, use the arrow keys to choose `JavaScript` and hit `Enter`.

Navigate to your new project directory and install the necessary dependencies:

```bash
cd react-router
npm i
```

Open the project's folder in your code editor:

```bash
code .
```

## Getting started

Run the following command in your terminal:

```bash
touch src/components/PokemonList.jsx
```

Add the following to `src/components/PokemonList.jsx`:

```jsx
const PokemonList = (props) => {
	return (
		<>
			<h2>Pokemon</h2>
			<ul>
				{props.pokemon.map((currentPokemon) => (
					<li key={currentPokemon.name}>
						{currentPokemon.name}
					</li>
				))}
			</ul>
		</>
	);
};

export default PokemonList;
```

Open `src/App.jsx` and replace its contents with the following:

```jsx
// src/App.jsx
import { useState } from 'react';
import PokemonList from './components/PokemonList';

const initialState = [
	{ _id: 1, name: 'bulbasaur', weight: 69, height: 7 },
	{ _id: 2, name: 'ivysaur', weight: 130, height: 10 },
	{ _id: 3, name: 'venusaur', weight: 1000, height: 20 },
	{ _id: 4, name: 'charmander', weight: 85, height: 6 },
	{ _id: 5, name: 'charmeleon', weight: 190, height: 11 },
];

const App = () => {
	const [pokemon, setPokemon] = useState(initialState);
	return (
		<>
			<h1>Pokemon!</h1>
			<PokemonList pokemon={pokemon} />
		</>
	);
};

export default App;
```

Start the dev server by running `npm run dev` in your terminal and the go to `localhost:5173` in your browser.