
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SnowshoeingRound',
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
    <rect fill="none" height="24" width="24"/><path d="M12.5,3.5c0-1.1,0.9-2,2-2s2,0.9,2,2c0,1.1-0.9,2-2,2S12.5,4.6,12.5,3.5z M20,11.91c0-0.49-0.36-0.9-0.84-0.98 c-1.53-0.25-2.79-1.16-3.47-2.35l-1-1.58c-0.4-0.6-1-1-1.7-1c-0.68,0-1.28,0.28-4.77,1.76C7.49,8.07,7,8.8,7,9.6V12 c0,0.55,0.45,1,1,1s1-0.45,1-1V9.58l1.79-0.7L9.2,17l-2.88,2.03l-1.14-1.47L4,18.5l2.38,3.04c0.51,0.65,1.16,1.15,1.88,1.41 c0.28,0.1,0.53,0.04,0.72-0.11c0.3-0.23,0.42-0.7,0.12-1.07c-0.08-0.1-0.2-0.17-0.31-0.22c-0.43-0.18-0.82-0.45-1.14-0.83l-0.08-0.1 l2.85-2.01c0.38-0.27,0.65-0.66,0.77-1.1l0.7-2.53l2.11,2v4.52h-2V23h3.87c0.82,0,1.61-0.21,2.26-0.61 c0.26-0.16,0.37-0.39,0.37-0.64c0-0.38-0.3-0.75-0.77-0.75c-0.13,0-0.26,0.04-0.37,0.1c-0.4,0.23-0.87,0.37-1.36,0.4l0-5.16 c0-0.55-0.23-1.07-0.62-1.45l-1.49-1.41l0.6-3c1.07,1.24,2.63,2.15,4.37,2.43C19.46,13.01,20,12.52,20,11.91z"/>
  </svg>
</template>
        