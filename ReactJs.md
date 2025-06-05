# React JS

## Hooks

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
6. useMemo
7. useCallback

## Component Communication

1. Props Drilling
2. Context API
3. State Lifting
4. Event Handlers

## Rendering Techniques

1. Conditional Rendering
2. Lists with .map()
3. Keys in Lists
