
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NoStrollerRound',
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
    <g><rect fill="none" height="24" width="24"/><path d="M8,20c0,1.1-0.9,2-2,2s-2-0.9-2-2s0.9-2,2-2S8,18.9,8,20z M14.3,4.1C13.03,3.4,11.56,3,10,3C8.77,3,7.61,3.26,6.54,3.71 l4.37,4.37L14.3,4.1z M20.49,21.9c0.39-0.39,0.39-1.02,0-1.41l-9.82-9.82L3.51,3.51c-0.39-0.39-1.02-0.39-1.41,0l0,0 c-0.39,0.39-0.39,1.02,0,1.41l7.26,7.26l-2.66,3.12c-0.55,0.65-0.09,1.65,0.76,1.65h6.66l1.17,1.17c-0.88,0.33-1.47,1.25-1.26,2.28 c0.15,0.76,0.78,1.39,1.54,1.54c1.03,0.21,1.95-0.38,2.28-1.26l1.2,1.2C19.46,22.29,20.09,22.29,20.49,21.9L20.49,21.9z M17,6.27 C17.58,5.59,17.97,5,18.65,5c0.68,0,1.22,0.52,1.33,1.21C20.08,6.66,20.48,7,20.96,7c0.55,0,1-0.45,1-1c0-0.06,0-0.11-0.01-0.16 l0-0.01C21.65,4.22,20.3,3,18.65,3c-1.66,0-2.54,1.27-3.18,2.03l-3.5,4.11L17,14.17V6.27z"/></g>
  </svg>
</template>
        