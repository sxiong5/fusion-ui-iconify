
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'UnfoldLessDoubleRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M14.46,5.7l-2.47,2.46L9.53,5.7c-0.39-0.39-1.02-0.39-1.41,0s-0.39,1.02,0,1.41l3.17,3.18c0.39,0.39,1.02,0.39,1.41,0 l3.17-3.18c0.39-0.39,0.39-1.02,0-1.41S14.85,5.31,14.46,5.7z"/><path d="M14.46,0.7l-2.47,2.46L9.53,0.7c-0.39-0.39-1.02-0.39-1.41,0s-0.39,1.02,0,1.41l3.17,3.18c0.39,0.39,1.02,0.39,1.41,0 l3.17-3.18c0.39-0.39,0.39-1.02,0-1.41S14.85,0.31,14.46,0.7z"/><path d="M9.54,23.3l2.47-2.46l2.46,2.46c0.39,0.39,1.02,0.39,1.41,0c0.39-0.39,0.39-1.02,0-1.41l-3.17-3.18 c-0.39-0.39-1.02-0.39-1.41,0l-3.17,3.18c-0.39,0.39-0.39,1.02,0,1.41C8.52,23.69,9.15,23.69,9.54,23.3z"/><path d="M9.54,18.29l2.47-2.45l2.46,2.46c0.39,0.39,1.02,0.39,1.41,0c0.39-0.39,0.39-1.02,0-1.41l-3.17-3.18 c-0.39-0.39-1.02-0.39-1.41,0l-3.17,3.17c-0.39,0.39-0.39,1.02,0,1.41S9.15,18.68,9.54,18.29z"/></g></g>
  </svg>
</template>
        