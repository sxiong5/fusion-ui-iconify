
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SwipeDownRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M8.83,19.1c-0.26-0.6,0.09-1.28,0.73-1.41l3.58-0.71L8.79,7.17c-0.34-0.76,0-1.64,0.76-1.98c0.76-0.34,1.64,0,1.98,0.76 l2.43,5.49l0.84-0.37c0.28-0.13,0.59-0.18,0.9-0.17l4.56,0.21c0.86,0.04,1.6,0.63,1.83,1.45l1.23,4.33 c0.27,0.96-0.2,1.97-1.11,2.37l-5.63,2.49c-0.48,0.21-1.26,0.33-1.76,0.14l-5.45-2.27C9.13,19.53,8.93,19.34,8.83,19.1z M5.59,2.73 C4.27,4.65,3.5,6.99,3.5,9.5c0,0.92,0.1,1.82,0.3,2.68l-1.19-1.19c-0.29-0.29-0.77-0.32-1.07-0.04c-0.31,0.29-0.31,0.78-0.02,1.08 l2.26,2.26c0.39,0.39,1.02,0.39,1.41,0l2.24-2.24c0.29-0.29,0.32-0.77,0.04-1.07c-0.29-0.31-0.78-0.31-1.08-0.02l-1.09,1.09 C5.11,11.24,5,10.38,5,9.5c0-2.2,0.68-4.24,1.83-5.93c0.2-0.3,0.17-0.7-0.09-0.95C6.41,2.28,5.86,2.34,5.59,2.73z"/></g>
  </svg>
</template>
        