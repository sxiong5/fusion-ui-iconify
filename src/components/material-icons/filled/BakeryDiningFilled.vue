
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BakeryDiningFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M19.28,16.34C18.07,15.45,17.46,15,17.46,15s0.32-0.59,0.96-1.78 c0.38-0.59,1.22-0.59,1.6,0l0.81,1.26c0.19,0.3,0.21,0.68,0.06,1l-0.22,0.47C20.42,16.49,19.76,16.67,19.28,16.34z M4.72,16.34 c-0.48,0.33-1.13,0.15-1.39-0.38L3.1,15.49c-0.15-0.32-0.13-0.7,0.06-1l0.81-1.26c0.38-0.59,1.22-0.59,1.6,0 C6.22,14.41,6.54,15,6.54,15S5.93,15.45,4.72,16.34z M15.36,9.37c0.09-0.68,0.73-1.06,1.27-0.75l1.59,0.9 c0.46,0.26,0.63,0.91,0.36,1.41L16.5,15h-1.8L15.36,9.37z M8.63,9.37L9.3,15H7.5l-2.09-4.08c-0.27-0.5-0.1-1.15,0.36-1.41l1.59-0.9 C7.89,8.31,8.54,8.69,8.63,9.37z M13.8,15h-3.6L9.46,8.12C9.39,7.53,9.81,7,10.34,7h3.3c0.53,0,0.94,0.53,0.88,1.12L13.8,15z" fill-rule="evenodd"/></g>
  </svg>
</template>
        