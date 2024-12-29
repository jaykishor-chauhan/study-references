# React Router Notes

Welcome to my notes on **React Router**! This document aims to provide a comprehensive understanding of how to effectively use React Router for navigation in React applications.

## Table of Contents
1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Core Concepts](#core-concepts)
4. [Usage Examples](#usage-examples)
5. [Advanced Topics](#advanced-topics)
6. [Conclusion](#conclusion)

---

### Introduction
React Router is a powerful library for handling routing in React applications. It enables navigation between views, maintaining the state, and implementing dynamic routing with ease.

---

### Installation
To start using React Router, you need to install it:

```bash
npm install react-router-dom
```

---

### Core Concepts
#### 1. Routes and Route Components
- Use `Route` to define a path and its associated component.
- Wrap your application in a `BrowserRouter` or `HashRouter`.

#### 2. Nested Routes
- Define routes inside other routes for hierarchical navigation.

#### 3. Link and NavLink
- Use `Link` for navigation without refreshing the page.
- Use `NavLink` for navigation with active link styling.

---

### Usage Examples
#### Basic Setup
```jsx
import React from 'react';
import { BrowserRouter as Router, Route, Routes, Link } from 'react-router-dom';

function App() {
  return (
    <Router>
      <nav>
        <Link to="/">Home</Link>
        <Link to="/about">About</Link>
      </nav>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </Router>
  );
}

function Home() {
  return <h2>Home Page</h2>;
}

function About() {
  return <h2>About Page</h2>;
}

export default App;
```

#### 404 Page
```jsx
<Route path="*" element={<NotFound />} />
```

---

### Advanced Topics
#### Programmatic Navigation
Use the `useNavigate` hook to navigate programmatically:
```jsx
import { useNavigate } from 'react-router-dom';

function Login() {
  const navigate = useNavigate();

  function handleLogin() {
    // Perform login logic
    navigate('/dashboard');
  }

  return <button onClick={handleLogin}>Login</button>;
}
```

#### Lazy Loading
```jsx
import React, { lazy, Suspense } from 'react';
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';

const Home = lazy(() => import('./Home'));
const About = lazy(() => import('./About'));

function App() {
  return (
    <Router>
      <Suspense fallback={<div>Loading...</div>}>
        <Routes>
          <Route path="/" element={<Home />} />
          <Route path="/about" element={<About />} />
        </Routes>
      </Suspense>
    </Router>
  );
}

export default App;
```

---

### Conclusion
React Router simplifies navigation in React applications. Mastering it can significantly enhance user experience in single-page applications (SPAs).
