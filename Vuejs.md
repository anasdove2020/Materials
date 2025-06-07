# VueJS 

## VueJS 

- JavaScript Framework
- Used to build interactive User Interface on website, especially Single Page Application 
(SPA) 

## Key Features:

- Declarative Rendering 
	- Write HTML with special Vue syntax
- Reactivity
	- When our data changes, the UI update automatically 
- Components 
	- We can break our UI into reusable building blocks
	
## Write Components

VueJs has 2 ways to write componenst:

1. Option API
- Old or classic way 
- We organize componenst code into options: data, method, computed ets.
- Easier to read for beginners
-Great for simple componenst


```
export default {
  data() {
    return {
      count: 0
    };
  },
  methods: {
    increase() {
      this.count++;
    }
  }
};
```

2. Composition API
- Newer or flexible way 
- We use the setup() function and compose logic with function 
- Great for large or complex componenst
- Better for code reuse

```
import { ref } from 'vue';

export default {
  setup() {
    const count = ref(0);
    const increase = () => count.value++;
    return { count, increase };
  }
};
```
	