
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DownhillSkiingRound',
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
    <rect fill="none" height="24" width="24"/><path d="M18.5,4.5c0,1.1-0.9,2-2,2s-2-0.9-2-2s0.9-2,2-2S18.5,3.4,18.5,4.5z M15.78,20.9l0.76,0.27c0.62,0.21,1.27,0.33,1.96,0.33 c0.68,0,1.34-0.12,1.95-0.33c0.27-0.09,0.57-0.02,0.78,0.18l0,0c0.39,0.4,0.23,1.06-0.3,1.24C20.17,22.86,19.35,23,18.5,23 c-0.86,0-1.68-0.14-2.45-0.41L2.7,17.72c-0.39-0.14-0.59-0.57-0.45-0.95l0,0c0.14-0.39,0.57-0.6,0.96-0.45l6.19,2.25l1.72-4.44 L7.55,10.4C6.65,9.46,6.87,7.93,8,7.28l3.48-2.01c1.1-0.64,2.52-0.1,2.91,1.11l0.33,1.08c0.44,1.42,1.48,2.57,2.83,3.14l0.29-0.89 c0.13-0.39,0.55-0.61,0.94-0.48h0c0.4,0.13,0.61,0.55,0.48,0.95l-0.6,1.85c-0.17,0.52-0.72,0.82-1.24,0.65 c-2.02-0.63-3.64-2.15-4.42-4.1l-2.53,1.45l2.23,2.55c0.49,0.56,0.63,1.34,0.36,2.04l-1.78,4.63l3.09,1.12l2.1-6.44h0l0,0 c0.46,0.18,0.94,0.31,1.44,0.41L15.78,20.9z"/>
  </svg>
</template>
        