
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'LinkOffRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M14,9h2.87c1.46,0,2.8,0.98,3.08,2.42c0.31,1.64-0.74,3.11-2.22,3.48l1.53,1.53c1.77-0.91,2.95-2.82,2.7-5.01 C21.68,8.86,19.37,7,16.79,7H14c-0.55,0-1,0.45-1,1C13,8.55,13.45,9,14,9z M3.51,3.51c-0.39-0.39-1.02-0.39-1.41,0 c-0.39,0.39-0.39,1.02,0,1.41l2.64,2.64c-1.77,0.91-2.95,2.82-2.7,5.01C2.32,15.14,4.63,17,7.21,17H10c0.55,0,1-0.45,1-1 c0-0.55-0.45-1-1-1H7.13c-1.46,0-2.8-0.98-3.08-2.42C3.74,10.94,4.8,9.47,6.27,9.1l2.12,2.12C8.16,11.41,8,11.68,8,12 c0,0.55,0.45,1,1,1h1.17l8.9,8.9c0.39,0.39,1.02,0.39,1.41,0c0.39-0.39,0.39-1.02,0-1.41L3.51,3.51z M14,11l1.71,1.71 C15.89,12.53,16,12.28,16,12c0-0.55-0.45-1-1-1H14z"/></g>
  </svg>
</template>
        