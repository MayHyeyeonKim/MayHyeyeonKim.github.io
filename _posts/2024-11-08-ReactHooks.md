---
layout: single
title: "React Hooks: Understanding the Core 12"
categories: [Frontend]
tags: [JavaScript, React, Hooks, Programming, Frontend]
search: true
---

### What Are React Hooks, and Why Are They Needed?

**React Hooks** are special functions that allow you to use **state** and **lifecycle** features in functional components. Previously, only class components could manage state and lifecycle methods, but with Hooks, functional components can handle complex state and behavior as well.

#### Why Are Hooks Important?

1. **Simplicity and Readability**: Hooks make functional components simpler and more readable. Without needing classes, you can manage complex state and lifecycle behavior, resulting in cleaner, more straightforward code.

2. **Reusability**: Hooks allow you to separate stateful logic from components, making it easier to reuse the same logic across multiple components. For example, you can create a custom Hook like `useFetchData` and use it in various components.

3. **Better State Management**: Unlike class components, Hooks enable you to manage multiple state values within a single component, allowing for more flexible and organized state management.

4. **Functional Programming Benefits**: Hooks leverage the benefits of functional programming, such as immutability and composability, which improve maintainability and scalability.

React Hooks are powerful tools that reduce code complexity, enhance logic reusability, and optimize performance in your applications.

React Hooks simplify component state and side-effect management, making functional components powerful and reusable. Let’s explore each of the main 12 Hooks, their uses, and why you’d choose each one.

### React Hooks Overview: The Core 12

#### 1. `useState`

- **Concept**: Manages state in functional components.
- **Why Use**: Simplifies stateful logic in functional components without needing classes.
- **Example**:

  ```javascript
  import { useState } from "react";

  function Counter() {
    const [count, setCount] = useState(0);
    return <button onClick={() => setCount(count + 1)}>Count: {count}</button>;
  }
  ```

#### 2. `useEffect`

- **Concept**: Handles side effects like data fetching, subscriptions, or DOM manipulation.
- **Why Use**: Runs code at specific component lifecycle stages in a declarative way.
- **Example**:

  ```javascript
  import { useEffect } from "react";

  function App() {
    useEffect(() => {
      document.title = "Component Mounted";
      return () => (document.title = "Component Unmounted");
    }, []);
    return <div>Hello World</div>;
  }
  ```

#### 3. `useContext`

- **Concept**: Provides access to context values without manually passing props.
- **Why Use**: Simplifies data sharing between components, especially in deeply nested structures.
- **Example**:

  ```javascript
  import { useContext } from "react";
  import { ThemeContext } from "./ThemeContext";

  function DisplayTheme() {
    const theme = useContext(ThemeContext);
    return <div>Current Theme: {theme}</div>;
  }
  ```

#### 4. `useReducer`

- **Concept**: Manages complex state logic using reducers, an alternative to `useState`.
- **Why Use**: Useful for managing complex state transitions or actions in a component.
- **Example**:

  ```javascript
  import { useReducer } from "react";

  function reducer(state, action) {
    switch (action.type) {
      case "increment":
        return { count: state.count + 1 };
      case "decrement":
        return { count: state.count - 1 };
      default:
        return state;
    }
  }

  function Counter() {
    const [state, dispatch] = useReducer(reducer, { count: 0 });
    return (
      <div>
        <button onClick={() => dispatch({ type: "decrement" })}>-</button>
        <span>{state.count}</span>
        <button onClick={() => dispatch({ type: "increment" })}>+</button>
      </div>
    );
  }
  ```

#### 5. `useCallback`

- **Concept**: Returns a memoized version of a callback function.
- **Why Use**: Optimizes performance by preventing unnecessary re-creations of functions.
- **Example**:

  ```javascript
  import { useState, useCallback } from "react";

  function Parent() {
    const [count, setCount] = useState(0);
    const increment = useCallback(() => setCount((c) => c + 1), []);

    return <Child onClick={increment} />;
  }

  function Child({ onClick }) {
    return <button onClick={onClick}>Increment</button>;
  }
  ```

#### 6. `useMemo`

- **Concept**: Memoizes a value to avoid expensive recalculations.
- **Why Use**: Increases performance by caching calculated values.
- **Example**:

  ```javascript
  import { useMemo } from "react";

  function ExpensiveComponent({ items }) {
    const expensiveCalculation = useMemo(() => {
      console.log("Calculating...");
      return items.reduce((a, b) => a + b, 0);
    }, [items]);

    return <div>Total: {expensiveCalculation}</div>;
  }
  ```

#### 7. `useRef`

- **Concept**: Provides a mutable reference to a DOM element or value.
- **Why Use**: Useful for directly accessing or modifying DOM elements or retaining values across renders without re-rendering.
- **Example**:

  ```javascript
  import { useRef } from "react";

  function FocusInput() {
    const inputRef = useRef(null);

    const handleFocus = () => {
      inputRef.current.focus();
    };

    return (
      <div>
        <input ref={inputRef} placeholder="Click the button to focus me" />
        <button onClick={handleFocus}>Focus Input</button>
      </div>
    );
  }
  ```

#### 8. `useLayoutEffect`

- **Concept**: Runs synchronously after all DOM mutations, before painting to the screen.
- **Why Use**: Needed for DOM measurements or operations that must be applied immediately before the browser repaints.
- **Example**:

  ```javascript
  import { useLayoutEffect, useRef } from "react";

  function MeasureLayout() {
    const divRef = useRef(null);

    useLayoutEffect(() => {
      if (divRef.current) {
        console.log("Width:", divRef.current.offsetWidth);
        console.log("Height:", divRef.current.offsetHeight);
      }
    }, []);

    return (
      <div
        ref={divRef}
        style={{
          width: "100px",
          height: "100px",
          backgroundColor: "lightblue",
        }}
      >
        Measure Me
      </div>
    );
  }
  ```

#### 9. `useDebugValue`

- **Concept**: Custom hook debugging in React DevTools.
- **Why Use**: Useful for adding custom labels or descriptions to custom hooks, making them easier to debug.
- **Example**:

  ```javascript
  import { useDebugValue, useState } from "react";

  function useCustomHook(value) {
    const [state, setState] = useState(value);

    // Adds a label in React DevTools to show the current state
    useDebugValue(state ? "Active" : "Inactive");

    return [state, setState];
  }

  function ExampleComponent() {
    const [isActive] = useCustomHook(true);
    return <div>{isActive ? "Active" : "Inactive"}</div>;
  }
  ```

#### 10. `useImperativeHandle`

- **Concept**: Customizes the ref exposed to the parent component.
- **Why Use**: Allows control over what functions/values are available when the parent component accesses a child’s ref.
- **Example**:

  ```javascript
  import { forwardRef, useImperativeHandle, useRef } from "react";

  const FancyInput = forwardRef((props, ref) => {
    const inputRef = useRef();

    useImperativeHandle(ref, () => ({
      focus: () => {
        inputRef.current.focus();
      },
      clear: () => {
        inputRef.current.value = "";
      },
    }));

    return <input ref={inputRef} placeholder="Type something here" />;
  });

  function ParentComponent() {
    const inputRef = useRef();

    return (
      <div>
        <FancyInput ref={inputRef} />
        <button onClick={() => inputRef.current.focus()}>Focus Input</button>
        <button onClick={() => inputRef.current.clear()}>Clear Input</button>
      </div>
    );
  }
  ```

#### 11. `useTransition`

- **Concept**: Manages UI transitions by marking updates as low-priority.
- **Why Use**: Improves user experience in complex interfaces by allowing less critical updates to happen smoothly without blocking more urgent ones.
- **Example**:

  ```javascript
  import { useState, useTransition } from "react";

  function App() {
    const [isPending, startTransition] = useTransition();
    const [count, setCount] = useState(0);

    function handleClick() {
      startTransition(() => {
        setCount((c) => c + 1);
      });
    }

    return (
      <div>
        <button onClick={handleClick}>Increment</button>
        <p>Count: {count}</p>
        {isPending && <p>Updating...</p>}
      </div>
    );
  }
  ```

#### 12. `useDeferredValue`

- **Concept**: Delays updating a state variable to optimize performance.
- **Why Use**: Useful for rendering delayed state updates to reduce load on complex UI, especially in cases where immediate updates aren't critical.
- **Example**:

  ```javascript
  import { useState, useDeferredValue } from "react";

  function SearchList({ query }) {
    const deferredQuery = useDeferredValue(query);

    return (
      <div>
        <p>Searching for: {deferredQuery}</p>
        {/* Assume a list of search results based on deferredQuery */}
      </div>
    );
  }

  function App() {
    const [query, setQuery] = useState("");

    const handleChange = (e) => {
      setQuery(e.target.value);
    };

    return (
      <div>
        <input
          type="text"
          value={query}
          onChange={handleChange}
          placeholder="Type to search..."
        />
        <SearchList query={query} />
      </div>
    );
  }
  ```
