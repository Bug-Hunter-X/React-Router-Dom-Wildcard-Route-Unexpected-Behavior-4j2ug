# React Router Dom Wildcard Route Issue

This repository demonstrates a subtle bug in React Router Dom v6 related to the wildcard route (`/*`).  The issue arises when the wildcard route is placed after other, more specific routes.  Even if a route matches, the wildcard route can unexpectedly take precedence, leading to incorrect rendering of components.  The solution involves carefully ordering the routes within the `Routes` component to ensure correct matching.

## Setup

1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.

## Bug Demonstration

The `bug.js` file contains the buggy implementation. Notice that the `/*` route, despite coming after other routes, will always take precedence. This means that even if you navigate to `/about`, the `NotFound` component will be rendered.

## Solution

The `bugSolution.js` file demonstrates how to fix the bug. By re-ordering the routes, placing the wildcard route as the last element in the `Routes` component ensures that only when no other routes match, will the wildcard route be used. This prevents unintended matching of previously defined routes. 