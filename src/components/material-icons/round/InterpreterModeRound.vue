
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'InterpreterModeRound',
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
    <rect fill="none" height="24" width="24"/><path d="M20.5,16.5c-0.83,0-1.5-0.67-1.5-1.5v-2.5c0-0.83,0.67-1.5,1.5-1.5s1.5,0.67,1.5,1.5V15C22,15.83,21.33,16.5,20.5,16.5z M20.5,20c0.28,0,0.5-0.22,0.5-0.5c0-0.45,0-1.04,0-1.04c1.51-0.22,2.71-1.4,2.95-2.89C24,15.27,23.76,15,23.46,15 c-0.24,0-0.45,0.17-0.49,0.41c-0.2,1.18-1.23,2.09-2.47,2.09s-2.27-0.9-2.47-2.09C17.99,15.17,17.78,15,17.54,15 c-0.3,0-0.54,0.27-0.5,0.57c0.25,1.5,1.45,2.68,2.95,2.89c0,0,0,0.59,0,1.04C20,19.78,20.22,20,20.5,20z M9,12c-2.21,0-4-1.79-4-4 c0-2.21,1.79-4,4-4c0.47,0,0.92,0.08,1.34,0.23C9.5,5.26,9,6.57,9,8c0,1.43,0.5,2.74,1.34,3.77C9.92,11.92,9.47,12,9,12z M7.11,13.13C5.79,14.05,5,15.57,5,17.22V20H1v-2.78c0-1.12,0.61-2.15,1.61-2.66C3.85,13.92,5.37,13.37,7.11,13.13z M11,8 c0-2.21,1.79-4,4-4s4,1.79,4,4c0,2.21-1.79,4-4,4S11,10.21,11,8z M18.32,20c-1.67-0.81-2.82-2.52-2.82-4.5 c0-0.89,0.23-1.73,0.64-2.45C15.77,13.02,15.39,13,15,13c-2.53,0-4.71,0.7-6.39,1.56C7.61,15.07,7,16.1,7,17.22V20L18.32,20z"/>
  </svg>
</template>
        