
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AddTaskRound',
  props: svgIconProps,
  setup(props) {
    const fontSize = computed(() => {
      const _size = +props.size;
      if (isNaN(_size)) {
        const [_, size, unit] = /(d+)(w+)/.exec(props.size as string) || [];
        return unit === 'px' ? pxToRem(+size) : props.size;
      } else {
        return pxToRem(_size);
      }
    });

    return {
      fontSize,
      color: props.color
    };
  }
}
</script>

<template>
  <svg class="fn-icon-material fn-icon"
    :style="{ '--fn-icon-font-size': fontSize, '--fn-icon-color': $props.color }"
     xmlns="http://www.w3.org/2000/svg" enable-background="new 0 0 24 24" height="24" viewBox="0 0 24 24" width="24"
  >
    <rect fill="none" height="24" width="24"/><path d="M21.29,5.89l-10,10c-0.39,0.39-1.02,0.39-1.41,0l-2.83-2.83c-0.39-0.39-0.39-1.02,0-1.41l0,0c0.39-0.39,1.02-0.39,1.41,0 l2.12,2.12l9.29-9.29c0.39-0.39,1.02-0.39,1.41,0v0C21.68,4.87,21.68,5.5,21.29,5.89z M12,20c-4.71,0-8.48-4.09-7.95-8.9 c0.39-3.52,3.12-6.41,6.61-6.99c1.81-0.3,3.53,0.02,4.99,0.78c0.39,0.2,0.86,0.13,1.17-0.18l0,0c0.48-0.48,0.36-1.29-0.24-1.6 C15.11,2.36,13.45,1.95,11.68,2c-5.14,0.16-9.41,4.34-9.67,9.47C1.72,17.24,6.3,22,12,22c1.2,0,2.34-0.21,3.41-0.6 c0.68-0.25,0.87-1.13,0.35-1.65l0,0c-0.27-0.27-0.68-0.37-1.04-0.23C13.87,19.83,12.95,20,12,20z M19,15h-2c-0.55,0-1,0.45-1,1v0 c0,0.55,0.45,1,1,1h2v2c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v-2h2c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h-2v-2c0-0.55-0.45-1-1-1 h0c-0.55,0-1,0.45-1,1V15z"/>
  </svg>
</template>
        