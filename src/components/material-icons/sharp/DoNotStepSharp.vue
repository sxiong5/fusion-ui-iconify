
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DoNotStepSharp',
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
    <g><rect fill="none" height="24" width="24"/><path d="M1.39,4.22l8.24,8.24l-0.69,0.72L6.87,11.1c-0.11,0.4-0.26,0.78-0.45,1.12l1.75,1.75l-0.69,0.72l-1.63-1.63 c-0.24,0.29-0.5,0.56-0.77,0.8l1.63,1.63l-0.7,0.72l-1.74-1.74C2.83,15.43,1.34,15.82,1,15.92L1,20h9.5l3.33-3.33l5.94,5.94 l1.41-1.41L2.81,2.81L1.39,4.22z M18.51,15.68l-1.41-1.41l4.48-4.48L23,11.2L18.51,15.68z M20.88,9.08l-4.48,4.48L9.3,6.47L13.8,2 L20.88,9.08z"/></g>
  </svg>
</template>
        