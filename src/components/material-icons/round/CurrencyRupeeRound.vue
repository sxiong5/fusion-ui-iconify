
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CurrencyRupeeRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M10.5,14H9.77l5.1,5.31c0.61,0.64,0.16,1.69-0.72,1.69c-0.27,0-0.53-0.11-0.72-0.31L7.4,14.41C7.14,14.15,7,13.79,7,13.43 C7,12.64,7.64,12,8.43,12h2.07c1.76,0,3.22-1.3,3.46-3L7,9C6.45,9,6,8.55,6,8s0.45-1,1-1l6.66,0C13.1,5.82,11.9,5,10.5,5L7,5 C6.45,5,6,4.55,6,4s0.45-1,1-1h10c0.55,0,1,0.45,1,1s-0.45,1-1,1l-2.26,0c0.48,0.58,0.84,1.26,1.05,2L17,7c0.55,0,1,0.45,1,1 s-0.45,1-1,1l-1.02,0C15.72,11.8,13.36,14,10.5,14z"/></g>
  </svg>
</template>
        