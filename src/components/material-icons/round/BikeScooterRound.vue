
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BikeScooterRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M10,14h0.74L8.82,5.56C8.61,4.65,7.8,4,6.87,4H4C3.45,4,3,4.45,3,5v0c0,0.55,0.45,1,1,1h2.87l1.42,6.25c0,0-0.01,0-0.01,0 C6.12,12.9,4.47,14.73,4.09,17H0v2h6v-1C6,15.79,7.79,14,10,14z"/><path d="M18.75,8l-0.56,0l-1.35-3.69C16.55,3.52,15.8,3,14.96,3H12c-0.55,0-1,0.45-1,1v0c0,0.55,0.45,1,1,1h2.96l1.1,3H10.4 l0.46,2H15c-0.43,0.58-0.75,1.25-0.9,2h-2.79l0.46,2h2.33c0.44,2.23,2.31,3.88,4.65,3.99c3.16,0.15,5.88-2.83,5.12-6.1 C23.34,9.57,21.13,8,18.75,8z M18.88,16c-1.54-0.06-2.84-1.37-2.88-2.92c-0.02-0.96,0.39-1.8,1.05-2.36l0.62,1.7 c0.19,0.52,0.76,0.79,1.28,0.6l0,0c0.52-0.19,0.79-0.76,0.6-1.28l-0.63-1.73c0,0,0,0,0.01-0.01C20.64,9.96,22,11.29,22,13 C22,14.72,20.62,16.06,18.88,16z"/><path d="M10,15c-1.66,0-3,1.34-3,3s1.34,3,3,3s3-1.34,3-3S11.66,15,10,15z M10,19c-0.55,0-1-0.45-1-1s0.45-1,1-1s1,0.45,1,1 S10.55,19,10,19z"/></g></g>
  </svg>
</template>
        