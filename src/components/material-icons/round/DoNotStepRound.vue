
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DoNotStepRound',
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
    <g><rect fill="none" height="24" width="24"/><path d="M2.1,3.51c-0.39,0.39-0.39,1.02,0,1.41l7.19,7.19c0.18,0.2,0.18,0.5-0.01,0.7c-0.1,0.1-0.23,0.15-0.35,0.15 s-0.26-0.05-0.35-0.15L6.87,11.1c-0.11,0.4-0.26,0.78-0.45,1.12l1.4,1.4c0.2,0.2,0.2,0.51,0,0.71c-0.1,0.1-0.23,0.15-0.35,0.15 s-0.26-0.05-0.35-0.15l-1.27-1.27c-0.24,0.29-0.5,0.56-0.77,0.8l1.28,1.28c0.2,0.2,0.2,0.51,0,0.71C6.26,15.95,6.13,16,6,16 s-0.26-0.05-0.35-0.15l-1.38-1.38c-0.71,0.47-1.43,0.81-2.02,1.04C1.49,15.81,1,16.55,1,17.37L1,18c0,1.1,0.9,2,2,2h6.67 c0.53,0,1.04-0.21,1.41-0.59l2.74-2.74l5.23,5.23c0.39,0.39,1.02,0.39,1.41,0l0,0c0.39-0.39,0.39-1.02,0-1.41L3.51,3.51 C3.12,3.12,2.49,3.12,2.1,3.51L2.1,3.51z M18.51,15.68l-1.41-1.41l4.48-4.48l0,0c0.78,0.78,0.78,2.05,0,2.83L18.51,15.68z M20.88,9.08l-4.48,4.48L9.3,6.47l3.09-3.07c0.78-0.78,2.04-0.77,2.82,0L20.88,9.08z"/></g>
  </svg>
</template>
        