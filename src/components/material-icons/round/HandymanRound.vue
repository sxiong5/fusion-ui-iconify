
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'HandymanRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><g><path d="M21.67,18.17l-4.72-4.72c-0.48-0.48-0.99-0.59-1.58-0.59l-2.54,2.54c0,0.59,0.11,1.11,0.59,1.58l4.72,4.72 c0.39,0.39,1.02,0.39,1.41,0l2.12-2.12C22.06,19.2,22.06,18.56,21.67,18.17z"/></g><g><path d="M16.63,9.49c0.39,0.39,1.02,0.39,1.41,0l0.71-0.71l2.12,2.12c1.17-1.17,1.17-3.07,0-4.24l-2.83-2.83 c-0.39-0.39-1.02-0.39-1.41,0l-0.71,0.71V2c0-0.62-0.76-0.95-1.21-0.5l-2.54,2.54c-0.45,0.45-0.12,1.21,0.5,1.21h2.54l-0.71,0.71 c-0.39,0.39-0.39,1.02,0,1.41l0.35,0.35l-2.89,2.89L7.85,6.48v-1c0-0.27-0.11-0.52-0.29-0.71L5.54,2.74 c-0.39-0.39-1.02-0.39-1.41,0L2.71,4.16c-0.39,0.39-0.39,1.02,0,1.41L4.73,7.6c0.19,0.19,0.44,0.29,0.71,0.29h1l4.13,4.13 l-0.85,0.85H8.42c-0.53,0-1.04,0.21-1.41,0.59l-4.72,4.72c-0.39,0.39-0.39,1.02,0,1.41l2.12,2.12c0.39,0.39,1.02,0.39,1.41,0 l4.72-4.72c0.38-0.38,0.59-0.88,0.59-1.41v-1.29l5.15-5.15L16.63,9.49z"/></g></g></g>
  </svg>
</template>
        