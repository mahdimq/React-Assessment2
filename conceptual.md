### Conceptual Exercise

Answer the following questions below:

- What is the purpose of the React Router?
  React Router is a client side routing that syncs the application with the URL. It allows us to build a single page web application with navigation without the page refreshing when the user navigates through the application. React Router uses Component structure to call components

- What is a single page application?
  Single page applications are web applications that use client side routing exclusively. They do not need to reload the page everytime a user navigates and uses JavaScript to manipulate the URL using a Web API.

- What are some differences between client side and server side routing?
  _Server-side routing:_
  Decides what HTML to return based on the URL requested.
  Clicking a link causes the browser to request the page and reload/replace the entire DOM.
  Everytime the user navigates the page, the browser makes a new requests to the server.
  It is the traditional way of routing.
  _Client-side routing:_
  These are single page web applications.
  Uses JavaScript to manipulate URL.
  The entire web application is loaded on the first request.
  Everytime a user navigates on the page, routing is handled internally by JS instead of making a new request.
  Better UI/UX.
  Generally requires more setup than traditional server-side routing.

* What are two ways of handling redirects with React Router? When would you use each?
  1.Using the <Redirect> component. We need to import "Redirect" from "react-router-dom", then add the path to call when the user is accesses an invalid URL or is redirected.
  2.Calling the ".push" method on the "history" object. We can access the "history" object by importing the "useHistory" hook from "react", then we wrap the history object over the browsers history API. The "history" object has a ".push(url)" which adds the url to the session history.

* What are two different ways to handle page-not-found user experiences using React Router?
  1.We can add a final <Route /> component at the bottom inside the <Switch /> component. This means is the routes above haven't matched, the only possible route would hit the one that does not actually exist.
  2.Using the <Link /> component to a "page-not-found" route.

- How do you grab URL parameters from within a component using React Router?
  We import the "useParams" Hook from "react-router". The "useParams" Hook then allows us to get any parameter that has been defined by a <Route /> with a path that has a colon (:) before the parameter.
  Example: <Route path="/something/:id" />

- What is context in React? When would you use it?
  Context is a way to allow some data to be accessible anywhere in the application. Usually, a prop can only be passed down to components via parent to child, even if a component doesn't need that prop, for it's child to be able to use that prop, it has to be passed down. This causes "prop-drilling" and lots of repitition and re-rendering of components that don't need to re-render.
  We create a context file and export it. Then wrap our parent component (which has the logic we need for other components to use) in a <UserContext.Provider>. For the components that need to use those props/logic, we inport the "useContext" Hook from react. This looks for the nearest matching context, and reads its value. When the value changes, the component re-renders.

- Describe some differences between class-based components and function
  components in React.
  -The most common difference is the syntax. Class based components are JavaScript classes wheres as functional components are JavaScript functions. Class component requires you to extend from React.Component and create a render function which returns a React element.
  -Previously, the only way to have state in a component is to create a class based components. Functional components used to be "dumb" or "state-less" components until the introduction of Hooks.
  -Functional components have significantly less code.
  -For class based components, props are passed down, and accessed using "this.props"
  -Class based components have 4 main lifecycle methods instead of a single useEffect. These are: render, componentDidMount, componentDidUpdate, componentWillUnmount.

- What are some of the problems that hooks were designed to solve?
  In functional components, Hooks solve the problem of:
  -Add and manage "state" using "useState".
  -Lifecycle methods using "useEffect".
  -Sharing non-visual logic (business logic) using "useContext". Previously the only way to share logic in class based methods were mixins or higher order components.
