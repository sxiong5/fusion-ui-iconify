
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NoFlashRound',
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
    <g><rect fill="none" height="24" width="24"/><path d="M3.16,3.16c-0.39-0.39-1.02-0.39-1.41,0l0,0c-0.39,0.39-0.39,1.02,0,1.41l4.6,4.6L6.14,9.4H3.6C2.72,9.4,2,10.12,2,11v9.4 C2,21.28,2.72,22,3.6,22h12.8c0.75,0,1.38-0.52,1.55-1.22l1.47,1.47c0.39,0.39,1.02,0.39,1.41,0l0,0c0.39-0.39,0.39-1.02,0-1.41 L3.16,3.16z M10,20c-2.21,0-4-1.79-4-4c0-1.95,1.4-3.57,3.25-3.92l1.57,1.57c-0.26-0.09-0.53-0.15-0.82-0.15 c-1.38,0-2.5,1.12-2.5,2.5c0,1.38,1.12,2.5,2.5,2.5c1.38,0,2.5-1.12,2.5-2.5c0-0.29-0.06-0.56-0.15-0.82l1.57,1.57 C13.57,18.6,11.95,20,10,20z M18,15.17L10.83,8h0.87c0.56,0,1.1,0.24,1.48,0.65l0.69,0.75h2.54c0.88,0,1.6,0.72,1.6,1.6V15.17z M20.4,5.6h0.75c0.38,0,0.62,0.41,0.44,0.74L19,11V7h-0.5C18.22,7,18,6.78,18,6.5v-4C18,2.22,18.22,2,18.5,2h2.73 c0.36,0,0.6,0.37,0.46,0.7L20.4,5.6z"/></g>
  </svg>
</template>
        