
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'EscalatorWarningRound',
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
    <g><rect fill="none" height="24" width="24"/><path d="M6.5,2c1.1,0,2,0.9,2,2s-0.9,2-2,2s-2-0.9-2-2S5.4,2,6.5,2z M15.5,9.5c0,0.83,0.67,1.5,1.5,1.5s1.5-0.67,1.5-1.5 S17.83,8,17,8S15.5,8.67,15.5,9.5z M18.5,12h-2.84c-0.58,0.01-1.14,0.32-1.45,0.86l-0.92,1.32L9.72,8C9.35,7.37,8.69,7.01,8.01,7H5 C3.9,7,3,7.9,3,9v5c0,0.55,0.45,1,1,1h0.5v6c0,0.55,0.45,1,1,1h3c0.55,0,1-0.45,1-1v-9.39l2.24,3.89c0.18,0.31,0.51,0.5,0.87,0.5 h1.1c0.33,0,0.63-0.16,0.82-0.43L15,14.9V21c0,0.55,0.45,1,1,1h2c0.55,0,1-0.45,1-1v-4h0c0.55,0,1-0.45,1-1v-2.5 C20,12.68,19.33,12,18.5,12z"/></g>
  </svg>
</template>
        