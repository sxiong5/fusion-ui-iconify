
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ManageHistoryFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M22.69,18.37l1.14-1l-1-1.73l-1.45,0.49c-0.32-0.27-0.68-0.48-1.08-0.63L20,14h-2l-0.3,1.49c-0.4,0.15-0.76,0.36-1.08,0.63 l-1.45-0.49l-1,1.73l1.14,1c-0.08,0.5-0.08,0.76,0,1.26l-1.14,1l1,1.73l1.45-0.49c0.32,0.27,0.68,0.48,1.08,0.63L18,24h2l0.3-1.49 c0.4-0.15,0.76-0.36,1.08-0.63l1.45,0.49l1-1.73l-1.14-1C22.77,19.13,22.77,18.87,22.69,18.37z M19,21c-1.1,0-2-0.9-2-2s0.9-2,2-2 s2,0.9,2,2S20.1,21,19,21z M11,7v5.41l2.36,2.36l1.04-1.79L13,11.59V7H11z M21,12c0-4.97-4.03-9-9-9C9.17,3,6.65,4.32,5,6.36V4H3v6 h6V8H6.26C7.53,6.19,9.63,5,12,5c3.86,0,7,3.14,7,7H21z M10.86,18.91C7.87,18.42,5.51,16.01,5.08,13H3.06c0.5,4.5,4.31,8,8.94,8 c0.02,0,0.05,0,0.07,0L10.86,18.91z"/></g>
  </svg>
</template>
        