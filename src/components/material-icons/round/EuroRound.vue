
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'EuroRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g/><path d="M15,18.5c-2.51,0-4.68-1.42-5.76-3.5h5.14c0.38,0,0.73-0.21,0.89-0.55l0,0c0.33-0.66-0.15-1.45-0.89-1.45h-5.8 c-0.05-0.33-0.08-0.66-0.08-1s0.03-0.67,0.08-1h5.8c0.38,0,0.73-0.21,0.89-0.55l0,0C15.61,9.78,15.13,9,14.38,9H9.24 C10.32,6.92,12.5,5.5,15,5.5c1.25,0,2.42,0.36,3.42,0.97c0.5,0.31,1.15,0.26,1.57-0.16l0,0c0.58-0.58,0.45-1.53-0.25-1.96 C18.36,3.5,16.73,3,15,3c-3.92,0-7.24,2.51-8.48,6h-2.9C3.24,9,2.89,9.21,2.72,9.55l0,0C2.39,10.22,2.87,11,3.62,11h2.44 C6.02,11.33,6,11.66,6,12s0.02,0.67,0.06,1H3.62c-0.38,0-0.73,0.21-0.89,0.55l0,0C2.39,14.22,2.87,15,3.62,15h2.9 c1.24,3.49,4.56,6,8.48,6c1.74,0,3.36-0.49,4.74-1.35c0.69-0.43,0.82-1.39,0.24-1.97l0,0c-0.42-0.42-1.07-0.47-1.57-0.15 C17.42,18.15,16.26,18.5,15,18.5z"/></g>
  </svg>
</template>
        