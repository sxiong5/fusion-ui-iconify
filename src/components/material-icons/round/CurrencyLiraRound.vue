
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CurrencyLiraRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M9,15.84l-1.47,0.92C6.86,17.18,6,16.7,6,15.91c0-0.34,0.18-0.66,0.47-0.85L9,13.48v-2.36l-1.47,0.92 C6.86,12.46,6,11.98,6,11.19c0-0.34,0.18-0.66,0.47-0.85L9,8.76V4c0-0.55,0.45-1,1-1s1,0.45,1,1v3.51l2.47-1.55 C14.14,5.54,15,6.02,15,6.81c0,0.34-0.18,0.66-0.47,0.85L11,9.87l0.01,2.35l2.46-1.54c0.67-0.42,1.53,0.06,1.53,0.85 c0,0.34-0.18,0.66-0.47,0.85L11,14.59V19c2.47,0,4.52-1.79,4.93-4.15c0.08-0.49,0.49-0.85,0.98-0.85c0.61,0,1.09,0.54,1,1.14 C17.37,18.46,14.48,21,11,21h-1c-0.55,0-1-0.45-1-1V15.84z"/></g>
  </svg>
</template>
        