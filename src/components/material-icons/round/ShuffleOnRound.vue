
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ShuffleOnRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M21,1H3C1.9,1,1,1.9,1,3v18c0,1.1,0.9,2,2,2h18c1.1,0,2-0.9,2-2V3C23,1.9,22.1,1,21,1z M4.3,4.7 c0.39-0.39,1.02-0.39,1.41,0l4.47,4.47l-1.42,1.4L4.3,6.11C3.91,5.72,3.91,5.09,4.3,4.7z M19.59,19.5c0,0.28-0.22,0.5-0.5,0.5H15.3 c-0.45,0-0.67-0.54-0.36-0.85l1.2-1.2l-3.13-3.13l1.41-1.41l3.13,3.14l1.19-1.19c0.31-0.32,0.85-0.1,0.85,0.35V19.5z M19.59,8.29 c0,0.45-0.54,0.67-0.85,0.36l-1.19-1.19L5.7,19.29c-0.39,0.39-1.02,0.39-1.41,0c-0.39-0.39-0.39-1.02,0-1.41L16.13,6.04l-1.19-1.19 C14.63,4.54,14.85,4,15.3,4h3.79c0.28,0,0.5,0.22,0.5,0.5V8.29z"/></g>
  </svg>
</template>
        