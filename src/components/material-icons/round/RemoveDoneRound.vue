
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'RemoveDoneRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M4.14,2.69L4.14,2.69c-0.39,0.39-0.39,1.02,0,1.41l9.67,9.67l-1.41,1.41l-3.54-3.53c-0.39-0.39-1.02-0.39-1.41,0l0,0 c-0.39,0.39-0.39,1.02,0,1.41l4.24,4.24c0.39,0.39,1.02,0.39,1.41,0l2.12-2.12l5.89,5.89c0.39,0.39,1.02,0.39,1.41,0l0,0 c0.39-0.39,0.39-1.02,0-1.41L5.55,2.69C5.16,2.3,4.53,2.3,4.14,2.69z M18.05,12.36l4.24-4.24c0.39-0.39,0.39-1.03-0.01-1.42l0,0 c-0.39-0.38-1.02-0.38-1.41,0.01l-4.24,4.24L18.05,12.36z M16.64,6.7L16.64,6.7c-0.39-0.39-1.02-0.39-1.41,0l-1.42,1.42l1.41,1.41 l1.42-1.42C17.03,7.72,17.03,7.09,16.64,6.7z M1.79,13.06l4.95,4.95l1.41-1.41L3.2,11.65c-0.39-0.39-1.02-0.39-1.41,0l0,0 C1.4,12.04,1.4,12.67,1.79,13.06z"/></g>
  </svg>
</template>
        