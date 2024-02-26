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

### Clear `App.jsx`

Open `src/App.jsx` and replace its contents with the following:

```jsx
// src/App.jsx
const pokemon = [
	{ id: 1, name: 'bulbasaur', weight: 69, height: 7 },
	{ id: 2, name: 'ivysaur', weight: 130, height: 10 },
	{ id: 3, name: 'venusaur', weight: 1000 , height: 20 },
	{ id: 4, name: 'charmander', weight: 85, height: 6 },
	{ id: 5, name: 'charmeleon', weight: 190, height: 11 },
]

const PokemonList = () => {
	return (
		<>
			<h2>Pokemon</h2>
			<ul>
				{pokemon.map((currentPokemon, index) => {
					return <li key={currentPokemon.name}>
						{currentPokemon.name}
					</li>
				})}
			</ul>
		</>
	)
}

const App = () => {

	return (
		<>
			<h1>Pokemon!</h1>
			<PokemonList />
		</>
	);

}

export default App
```

**NOTE:** For ease of learning, we've including multiple components in the same file along with the data.  In production, you would put each of these in a separate file, but to make learning easier let's keep them in `App.jsx` for now.  Feel free to move them into separate files, if you'd prefer.

Open the `main.jsx` file in the `src` directory and remove the following line:

```jsx
import './index.css'
```

Start the dev server by running `npm run dev` in your terminal and the go to `localhost:5173` in your browser.