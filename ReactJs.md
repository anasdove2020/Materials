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
4. useContext
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
