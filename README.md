# React Router Notes

Welcome to my notes on **React Router**! This document aims to provide a comprehensive understanding of how to effectively use React Router for navigation in React applications.

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
- Wrap your application in a `BrowserRouter`.

#### 2. Nested Routes
- Define routes inside other routes for hierarchical navigation.

#### 3. Link and NavLink
- Use `Link` for navigation without refreshing the page.
- Use `NavLink` for navigation with active link styling.

---

### Usage Examples
#### Basic Setup
```jsx
import './App.css';
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";

import Home from './components/pages/Home';
import Portfolio from './components/pages/Portfolio';

function App() {
  return (
    <div className="App">
      <Router>
        <Routes>
          <Route path="/" element={<Home />} />
          <Route path="/portfolio" element={<Portfolio />} />
        </Routes>
      </Router>
    </div>
  );
}

export default App;

```

#### 404 Page
```jsx
<Route path="*" element={<NotFound />} />
```

---
