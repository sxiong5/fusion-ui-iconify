
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CableRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M20,5V4c0-0.55-0.45-1-1-1h-2c-0.55,0-1,0.45-1,1v1h0c-0.55,0-1,0.45-1,1v3c0,0.55,0.45,1,1,1h1l0,6.91 c0,1.04-0.76,1.98-1.79,2.08C14.01,19.11,13,18.17,13,17l0-9.86c0-2.13-1.61-3.99-3.74-4.13C6.93,2.86,5,4.7,5,7v7H4 c-0.55,0-1,0.45-1,1v3c0,0.55,0.45,1,1,1h0v1c0,0.55,0.45,1,1,1h2c0.55,0,1-0.45,1-1v-1h0c0.55,0,1-0.45,1-1v-3c0-0.55-0.45-1-1-1 H7l0-6.91c0-1.04,0.76-1.98,1.79-2.08C9.99,4.89,11,5.83,11,7l0,9.86c0,2.13,1.61,3.99,3.74,4.13C17.07,21.14,19,19.3,19,17v-7h1 c0.55,0,1-0.45,1-1V6C21,5.45,20.55,5,20,5L20,5z"/></g></g>
  </svg>
</template>
        