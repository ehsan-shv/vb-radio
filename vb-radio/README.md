# vb-radio

<a href="https://www.npmjs.com/package/vb-radio"><img src="https://img.shields.io/npm/v/vb-radio.svg" alt="Version"></a>

**Vue 3 radio input component.**

> Support Vue3, Nuxt3 and type-safe.

## Instalation

```bash
npm i vb-radio
```

## Basic Example

```js
<template>
  <RadioGroup v-model="framework" name="frameworks" :options="frameworks" />
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { RadioGroup } from 'vb-input';

export default defineComponent({
  name: 'App',
  components: {
    RadioGroup,
  },
  setup() {
    const frameworks = ref([
      { label: 'Vue', value: 'vue' },
      { label: 'React', value: 'react' },
      { label: 'Angular', value: 'angular' },
      { label: 'Svelte', value: 'svelte' },
    ]);

    const framework = ref('vue');

    return { frameworks, framework };
  },
});
</script>
```

## Vertical Example

```js
<template>
  <RadioGroup :vertical="true" v-model="framework" name="frameworks" :options="frameworks" />
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { RadioGroup } from 'vb-input';

export default defineComponent({
  name: 'App',
  components: {
    RadioGroup,
  },
  setup() {
    const frameworks = ref([
      { label: 'Vue', value: 'vue' },
      { label: 'React', value: 'react' },
      { label: 'Angular', value: 'angular' },
      { label: 'Svelte', value: 'svelte' },
    ]);

    const framework = ref('vue');

    return { frameworks, framework };
  },
});
</script>
```

## RTL Example

```js
<template>
  <RadioGroup :rtl="true" v-model="framework" name="frameworks" :options="frameworks" />
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { RadioGroup } from 'vb-input';

export default defineComponent({
  name: 'App',
  components: {
    RadioGroup,
  },
  setup() {
    const frameworks = ref([
      { label: 'Vue', value: 'vue' },
      { label: 'React', value: 'react' },
      { label: 'Angular', value: 'angular' },
      { label: 'Svelte', value: 'svelte' },
    ]);

    const framework = ref('vue');

    return { frameworks, framework };
  },
});
</script>
```
