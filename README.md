This project is a very simple demo of Next.js.

## Intro to Next

Next provides a minimalistic framework for rendering React applications on the server. It provides:

* Server side rendering. Each route is defined by page. In other words, no need to map routes. 
* Automatic code splitting and lazy loading. It only loads what it needs when it needs it. If for example, you have a module that is used in more than half of your pages, next.js will make sure its part of the main JS bundle. If it is used in less than half of the pages, that module is put into the "pages bundle" meaning its only loaded when a page that requires it is loaded. This is a performance boost.
* Built in CSS support, vendor prefixing, plugins for preprocessing, ability to use styled components.
* Hot reload for during development.
* Simplfies deployment.

Page based routes are navigated to in the application using 'next/Link'

```
import Link from 'next/link';
const Nav = () => (
	<NavStyles>
		<Link href="/items">
			<a>Items</a>
		</Link>
```

A basic app could start from scratch, then "npm install --save next react react-dom". In the package.json script, add this:

```
  "scripts": {
    "dev": "next -p 7777",
    "build": "next build",
    "start": "next start",
```

Next, create a folder called "pages". Add an index.js. Notice we aren't importing react.

export default () => (<div>Hello world</div>);

```
npm run dev
```

Open http://localhost:3000, and you should see Hello world. To create an about page (with its own /about route), add pages/about.js.

export default() => (<div>About this fun project</div>);

Notice, there has been no need to add the base HTML page, DOCTYPE, etc. All of that is handled by Next.js.

## Notes

* I used the Cerulean bootstrap theme from https://bootswatch.com. See components/Layout.js
* pages/index.js grabs the data from the API in its getInitialProps method, and isomorphic-unfetch is used to fetch the data because it works on the server side
* A simple example of style jsx is commented out in components/Navbar.js

