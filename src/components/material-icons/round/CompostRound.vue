
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CompostRound',
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
    <rect fill="none" height="24" width="24"/><path d="M11.73,21.5c-4.95-0.14-9.08-4.27-9.22-9.22C2.35,6.91,6.67,2.5,12,2.5V1.21c0-0.45,0.54-0.67,0.85-0.35l2.79,2.79 c0.2,0.2,0.2,0.51,0,0.71l-2.79,2.79C12.54,7.46,12,7.24,12,6.79V5.5c-3.58,0-6.5,2.92-6.5,6.5c0,2.21,1.11,4.17,2.81,5.35 c0.51-0.92,1.63-1.62,2.98-1.8c-0.09-0.69-0.26-1.42-0.49-2.03c-0.33,0.28-0.75,0.46-1.22,0.48c-1.14,0.05-2.08-0.99-2.08-2.13 l0-0.86c0-0.29-0.05-0.57-0.14-0.83C7.24,9.84,7.5,9.49,7.86,9.52c1.3,0.09,3.6,0.52,3.64,2.48c0,0.29-0.06,0.56-0.17,0.8 C10.91,12.48,10.47,12.2,10,12c0.58,0.43,1.37,1.37,2,2.6c0.67-1.62,1.68-3.27,3-4.6c-0.76,0.52-1.47,1.12-2.13,1.81 c-0.26-0.42-0.4-0.93-0.36-1.47C12.59,9,13.79,8,15.13,8L16,8c0.56,0,0.97-0.14,1.28-0.31c0.34-0.19,0.76,0.05,0.75,0.44 C17.99,9.87,17.56,13,15,13c-0.49,0-0.94-0.14-1.32-0.38c-0.24,0.64-0.59,1.76-0.76,2.96c1.26,0.22,2.28,0.89,2.77,1.77 c1.57-1.09,2.64-2.85,2.79-4.87C18.5,12.22,18.71,12,18.98,12l1.82,0c0.47,0,0.71,0.24,0.69,0.52 C21.21,17.61,16.91,21.64,11.73,21.5z"/>
  </svg>
</template>
        