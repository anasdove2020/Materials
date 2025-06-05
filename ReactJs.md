# React JS

## Hooks

Means:
A Hook is a special function in React that lets you “hook into” React features like state, lifecycle, context, etc. — without writing a class component.

1. useState

Means:
- Let component remember things
- Tells React to store a value

```
import React, { useState } from 'react';

const [count, setCount] = useState(0);
```
   
2. useEffect

Means:
- Let us run code when something happen.
- Like when component:
  - mounts (shows up on screen)
  - updates (like a change in state)
  - unmounts (goes away)

Often used to:
- Fetch data
- Set up timer
- Listen to events

```
import React, { useEffect } from 'react';

  useEffect(() => {
    console.log('Hello! This runs once when the component loads.');
  }, []); // empty array = run only once
```

Dependency array:
- Tells React when to run the code inside useEffect
- Blank : Run only once
- [count] : Runs every time "count" changes

Mount + Unmount:
```
  useEffect(() => {
    console.log('Hello! I am mounted.');

    return () => {
      console.log('Goodbye! I am unmounted.');
    };
  }, []); // [] = run effect only once, cleanup on unmount
}
```

3. useRef

Means:
- A hook that gives us container or box that can hold a value.
- Does not cause rerender
- remember the value accross render
- Can be used to access DOM elements

Access DOM element:
```
import React, { useRef, useEffect } from 'react';

function InputFocus() {
  const inputRef = useRef(null);

  useEffect(() => {
    inputRef.current.focus(); // focus the input box on load
  }, []);

  return <input ref={inputRef} placeholder="I will be focused" />;
}
```

Note:
- Super useful when we want to interact with a DOM element directly (e.g, focus, scroll, measure size, etc)

4. useContext

Means:
- Super useful hook for sharing data between components without passing props manually at every level.
- Let us get a value from React Context
- React context is global variable for our component tree, like:
   - Current user
   - Theme (dark/light)
   - Language (i18n)
   - Authentication status
 
Example (Theme):
- Create a context
```
import React from 'react';

const ThemeContext = React.createContext('light'); // default: 'light'
```

- Provide a value
```
function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}
```

- Use context in child component
```
import React, { useContext } from 'react';

function Toolbar() {
  const theme = useContext(ThemeContext); // Access the context value
  return <div>The current theme is: {theme}</div>;
}
```

5. useReducer

Means:
- Hooks that helps us manage more complex state logic than useState
- Powerful version of useState
- Instead just setting state, we dispatch actions describing what happened.
- A reducer function decides how to update the state based on those actions.

Example:
- Basic syntax:
```
const [state, dispatch] = useReducer(reducer, initialState);
```

Means:
- state: current state object/value
- dispatch: function to send an action to update state
- reducer: function(state, action) => newState
- initialState: starting value of state

Simple example (Counter):
```
import React, { useReducer } from 'react';

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    case 'decrement':
      return { count: state.count - 1 };
    case 'reset':
      return { count: 0 };
    default:
      return state;
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, { count: 0 });

  return (
    <div>
      <p>Count: {state.count}</p>
      <button onClick={() => dispatch({ type: 'increment' })}>+1</button>
      <button onClick={() => dispatch({ type: 'decrement' })}>-1</button>
      <button onClick={() => dispatch({ type: 'reset' })}>Reset</button>
    </div>
  );
}

export default Counter;
```

6. useMemo

Means:
- A react hook that helps optimize performance by memoizing expensive calculations.
- It remembers the result of calculation.
- Only recomputes when its dependencies change.
- Avoid re-doing heavy work on every render.

Syntax:
```
const memoizedValue = useMemo(() => {
  // expensive calculation
  return someValue;
}, [dependencies]);
```

Example (Expensive Calculation):
```
import React, { useState, useMemo } from 'react';

function factorial(n) {
  console.log('Calculating factorial...');
  return n <= 1 ? 1 : n * factorial(n - 1);
}

function FactorialCalculator() {
  const [number, setNumber] = useState(5);
  const [dummy, setDummy] = useState(false);

  const fact = useMemo(() => factorial(number), [number]);

  return (
    <div>
      <input
        type="number"
        value={number}
        onChange={(e) => setNumber(+e.target.value)}
      />
      <p>Factorial: {fact}</p>

      <button onClick={() => setDummy(!dummy)}>
        Re-render without changing number
      </button>
    </div>
  );
}

export default FactorialCalculator;
```

7. useCallback

Means:
- A react hook closely to useMemo, but for functions.
- It memoize a function, so React re-creates it only when dependency change.
- Helps optimize performance

Syntax:
```
const memoizedCallback = useCallback(() => {
  // function code here
}, [dependencies]);
```

Example (Optimizing child component render):
```
import React, { useState, useCallback } from 'react';

function Button({ onClick, children }) {
  console.log('Button render:', children);
  return <button onClick={onClick}>{children}</button>;
}

function Counter() {
  const [count, setCount] = useState(0);
  const [other, setOther] = useState(false);

  // Without useCallback, handleClick is recreated every render
  const handleClick = useCallback(() => {
    setCount(c => c + 1);
  }, []); // no dependencies → never re-created

  return (
    <div>
      <p>Count: {count}</p>
      <Button onClick={handleClick}>Increment</Button>

      <button onClick={() => setOther(o => !o)}>
        Toggle Other State
      </button>
    </div>
  );
}

export default Counter;
```

## Component Communication

1. Props Drilling
2. Context API
3. State Lifting
4. Event Handlers

## Rendering Techniques

1. Conditional Rendering
2. Lists with .map()
3. Keys in Lists
