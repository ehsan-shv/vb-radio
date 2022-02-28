<template>
  <div class="vb-radio" :class="{ vertical, rtl }">
    <input type="radio" :checked="modelValue === value" :value="value" v-bind="$attrs" class="vb-radio__field" />
    <label @click="onLabelClick" class="vb-radio__label" :class="{ rtl }">{{ label }}</label>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Radio',
  inheritAttrs: false,
  props: {
    label: {
      type: String,
      default: '',
    },
    modelValue: {
      type: [String, Number],
      default: '',
    },
    value: {
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
  setup(props, { emit }) {
    const onLabelClick = () => {
      emit('update:modelValue', props.value);
    };

    return { onLabelClick };
  },
});
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --vb-radio-color-default: #212121;
  --vb-radio-color-secondary: #9e9e9e;
  --vb-radio-backgrond-color: #2196f3;
  --vb-radio-elemen-margin: 20px;
}

.vb-radio {
  display: inline-flex;

  &:not(:last-child) {
    margin: 0 var(--vb-radio-elemen-margin) 0 0;
  }

  &.rtl {
    &:not(:last-child) {
      margin: 0 0 0 var(--vb-radio-elemen-margin);
    }
  }

  &.vertical {
    display: flex;

    &:not(:last-child) {
      margin: 0 0 var(--vb-radio-elemen-margin) 0;
    }
  }

  &__field {
    display: none !important;

    &:checked + label {
      &::after {
        background-color: var(--vb-radio-backgrond-color);
        border: 1px solid var(--vb-radio-backgrond-color);
      }
    }
  }

  &__label {
    position: relative;
    display: inline-flex;
    height: 20px;
    padding: 2px 0 0 28px;
    cursor: pointer;
    user-select: none;
    color: var(--vb-radio-color-default);
    font-size: 16px;
    &.rtl {
      text-align: right;
      padding: 2px 28px 0 0;

      &::before,
      &::after {
        left: unset;
        right: 0;
      }
    }
    &::before,
    &::after {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: calc(20px - 2px);
      height: calc(20px - 2px);
      border-radius: 100px;
    }
    &::before {
      border: 1px solid var(--vb-radio-color-secondary);
    }

    &::after {
      transform: scale(0.5);
    }
  }
}
</style>
