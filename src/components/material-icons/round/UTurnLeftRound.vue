
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'UTurnLeftRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M3.71,12.29c0.39-0.39,1.02-0.39,1.41,0L6,13.17V9c0-3.31,2.69-6,6-6s6,2.69,6,6v11c0,0.55-0.45,1-1,1s-1-0.45-1-1V9 c0-2.21-1.79-4-4-4S8,6.79,8,9v4.17l0.88-0.88c0.39-0.39,1.02-0.39,1.41,0c0.39,0.39,0.39,1.02,0,1.41l-2.59,2.59 c-0.39,0.39-1.02,0.39-1.41,0l-2.59-2.59C3.32,13.32,3.32,12.68,3.71,12.29z"/></g>
  </svg>
</template>
        