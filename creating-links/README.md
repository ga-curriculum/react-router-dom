# ![React Router - Creating Links](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create navigable links within their React application that update the browser's URL path.

## Understanding the `<Link>` component

React Router provides a `<Link>` component designed specifically for SPAs, that behaves much like the HTML `<a>` tag. The `<Link>` component allows users to change the path of the browser URL with a click, just like traditional web links.

Take a look at the example of a `<Link>` component below:

```jsx
<Link to='/'>Home</Link>
```

The `<Link>` component differs from a traditional `<a>` tag, in that it accepts a `to` prop instead of an `href`. The `to` prop is used to specify the navigation target. This prop can be a string representing the path or an object with more detail.

## Creating a navigation bar

Let's add some basic navigation to our application. Below the `<h1>Pokemon!</h1>` in your `<App>` component, insert the following HTML structure:

```jsx
// src/App.jsx
<nav>
  <ul>
    <li>Home</li>
    <li>Pokemon</li>
  </ul>
</nav>
```

This setup prepares us for integrating navigable links.

## Implementing links

At the top of `src/App.jsx`, we'll import `Link` from `react-router-dom`:

```jsx
// src/App.jsx
import { Link } from 'react-router-dom';
```

Next, update the list items in the navigation bar by wrapping their content with a `<Link>` component:

```jsx
// src/App.jsx
<nav>
  <ul>
    <li>
      <Link to='/'>Home</Link>
    </li>
    <li>
      <Link to='/pokemon'>Pokemon</Link>
    </li>
  </ul>
</nav>
```

This transforms the text content into clickable links, allowing our users to navigate to the URL path defined in each `<Link>`.

After adding the `<Link>` components, test out the navigation in your browser. Clicking on the links should change the URL path accordingly, but not the content displayed in your app. Although we are able to navigate between different locations in our app, we have yet to define what should be rendered at each of these locations. For that, we'll need to make use of React Router's `<Routes>` component.