
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'EarbudsBatterySharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><polygon points="20,7 20,6 18,6 18,7 16,7 16,18 22,18 22,7"/><path d="M5.38,16.5L5.38,16.5c-1.04,0-1.88-0.84-1.88-1.87V10H6V6H4C2.9,6,2,6.9,2,8v6.63C2,16.49,3.51,18,5.37,18h0 c1.86,0,3.37-1.51,3.37-3.37V9.37c0-1.04,0.84-1.87,1.87-1.87h0c1.04,0,1.87,0.84,1.87,1.87V14H10v4h2c1.1,0,2-0.9,2-2V9.37 C14,7.51,12.49,6,10.63,6h0C8.76,6,7.25,7.51,7.25,9.37v5.25C7.25,15.66,6.41,16.5,5.38,16.5z"/></g></g>
  </svg>
</template>
        