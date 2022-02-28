<template>
  <div class="vb-radioGroup">
    <Radio
      v-for="option in options"
      :key="option.value"
      :label="option.label"
      :value="option.value"
      :modelValue="modelValue"
      :name="name"
      :rtl="rtl"
      :vertical="vertical"
      @update:modelValue="$emit('update:modelValue', $event)"
    />
  </div>
</template>

<script>
import Radio from './Radio.vue';
export default {
  components: { Radio },
  name: 'RadioGruop',
  props: {
    options: {
      type: Array,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    modelValue: {
      type: [String, Number],
      required: true,
    },
    vertical: {
      type: Boolean,
      default: false,
    },
    rtl: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
