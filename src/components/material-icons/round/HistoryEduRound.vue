
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'HistoryEduRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M9,5v0.38c-0.83-0.33-1.72-0.5-2.61-0.5c-1.42,0-2.84,0.43-4.05,1.29C1.83,6.53,1.77,7.26,2.21,7.7l2.57,2.57h1.11v1.11 c0.86,0.86,1.98,1.31,3.11,1.36V15H7c-0.55,0-1,0.45-1,1v2c0,1.1,0.9,2,2,2h10c1.66,0,3-1.34,3-3V5c0-0.55-0.45-1-1-1H10 C9.45,4,9,4.45,9,5z M7.89,10.41V8.26H5.61L4.57,7.22C5.14,7,5.76,6.88,6.39,6.88c1.34,0,2.59,0.52,3.54,1.46l1.41,1.41l-0.2,0.2 c-0.51,0.51-1.19,0.8-1.92,0.8C8.75,10.75,8.29,10.63,7.89,10.41z M19,17c0,0.55-0.45,1-1,1s-1-0.45-1-1v-1c0-0.55-0.45-1-1-1h-5 v-2.59c0.57-0.23,1.1-0.57,1.56-1.03l0.2-0.2L15.59,14H17v-1.41l-6-5.97V6h8V17z"/></g></g>
  </svg>
</template>
        