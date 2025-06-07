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

## Single File Component - CompositionAPI
- Write component without returning anything from the setup() function
- This is possible because of <script></script>, which is a compiler macro that makes composition API code simpler and more concise.

```
<!-- Counter.vue -->
<template>
  <button @click="count++">Count: {{ count }}</button>
</template>

<script setup>
import { ref } from 'vue';

const count = ref(0); // No need to return it — automatically available in <template>
</script>
```

## Directives

Directives means:
- Special attributes in template that tell Vue to do something with DOM 
- Show or Hide 
- Loop
- Bind Data

Vue Directives: 
1. v-bind
2. v-model 
3. v- if (v-else, v-else-if)
4. v-show
5. v-for
6. v-on 

### v-bind

v-bind means:
- Bind a value from javascritpt code to HTML attributes
- Keep attribute in sync with our data 

1. Bind an Image scr and alt
```
<template>
  <img :src="imageUrl" :alt="imageAlt" width="200" />
</template>

<script setup>
import { ref } from 'vue';

const imageUrl = ref('https://picsum.photos/200');
const imageAlt = ref('Random image from Picsum');
</script>
```

2. Bind Class and Style 
```
<template>
  <div :class="boxClass" :style="boxStyle">
    This box has dynamic class and style!
  </div>
</template>

<script setup>
import { ref } from 'vue';

const boxClass = ref('highlighted');
const boxStyle = ref({
  backgroundColor: 'lightblue',
  padding: '10px',
  borderRadius: '8px'
});
</script>

<style>
.highlighted {
  border: 2px solid blue;
}
</style>
```

### v-model

v-model means: 
- Creates two-way binding between a from input our data.
- When user type in input, the data updates
- When the data changes, the input updates too

1. Text Input 
```
<template>
  <input v-model="name" placeholder="Enter your name" />
  <p>Hello, {{ name }}</p>
</template>

<script setup>
import { ref } from 'vue';
const name = ref('');
</script>
```

2. Textarea
```
<template>
  <textarea v-model="message" placeholder="Type your message..."></textarea>
  <p>Message: {{ message }}</p>
</template>

<script setup>
import { ref } from 'vue';
const message = ref('');
</script>
```

3. Checkbox
```
<template>
  <label>
    <input type="checkbox" v-model="accepted" />
    Accept Terms
  </label>
  <p>Accepted: {{ accepted }}</p>
</template>

<script setup>
import { ref } from 'vue';
const accepted = ref(false);
</script>
```

4. Checkbox with Multiple Values (Array Binding)
```
<template>
  <label><input type="checkbox" value="HTML" v-model="skills" /> HTML</label>
  <label><input type="checkbox" value="CSS" v-model="skills" /> CSS</label>
  <label><input type="checkbox" value="JavaScript" v-model="skills" /> JavaScript</label>
  <p>Selected Skills: {{ skills }}</p>
</template>

<script setup>
import { ref } from 'vue';
const skills = ref([]);
</script>
```

5. Radio Button
```
<template>
  <label><input type="radio" value="Male" v-model="gender" /> Male</label>
  <label><input type="radio" value="Female" v-model="gender" /> Female</label>
  <p>Selected: {{ gender }}</p>
</template>

<script setup>
import { ref } from 'vue';
const gender = ref('');
</script>
```

6. Dropdown or Select 
```
<template>
  <select v-model="selectedFruit">
    <option disabled value="">Select a fruit</option>
    <option>Apple</option>
    <option>Banana</option>
    <option>Cherry</option>
  </select>
  <p>You selected: {{ selectedFruit }}</p>
</template>

<script setup>
import { ref } from 'vue';
const selectedFruit = ref('');
</script>
```













































	