
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'UnfoldMoreDoubleRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M9.53,5.29L12,2.83l2.46,2.46c0.39,0.39,1.02,0.39,1.41,0s0.39-1.02,0-1.41L12.7,0.7c-0.39-0.39-1.02-0.39-1.41,0 L8.12,3.88c-0.39,0.39-0.39,1.02,0,1.41S9.14,5.68,9.53,5.29z"/><path d="M9.53,10.29L12,7.83l2.46,2.46c0.39,0.39,1.02,0.39,1.41,0s0.39-1.02,0-1.41L12.7,5.7c-0.39-0.39-1.02-0.39-1.41,0 L8.12,8.88c-0.39,0.39-0.39,1.02,0,1.41S9.14,10.68,9.53,10.29z"/><path d="M14.47,13.71L12,16.17l-2.46-2.46c-0.39-0.39-1.02-0.39-1.41,0c-0.39,0.39-0.39,1.02,0,1.41l3.17,3.18 c0.39,0.39,1.02,0.39,1.41,0l3.17-3.18c0.39-0.39,0.39-1.02,0-1.41C15.49,13.32,14.86,13.32,14.47,13.71z"/><path d="M14.47,18.72L12,21.17l-2.46-2.46c-0.39-0.39-1.02-0.39-1.41,0c-0.39,0.39-0.39,1.02,0,1.41l3.17,3.18 c0.39,0.39,1.02,0.39,1.41,0l3.17-3.17c0.39-0.39,0.39-1.02,0-1.41S14.86,18.33,14.47,18.72z"/></g></g>
  </svg>
</template>
        