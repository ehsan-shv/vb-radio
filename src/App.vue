<template>
  <h2>Main Stack:</h2>
  <RadioGroup v-model="framework" :vertical="true" name="frameworks" :options="frameworks" />
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import RadioGroup from './components/RadioGroup.vue';

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

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  padding: 80px;

  h2 {
    margin-bottom: 40px;
  }
}
</style>
