
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'PlagiarismRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M19.41,7.41l-4.83-4.83C14.21,2.21,13.7,2,13.17,2H6C4.9,2,4,2.9,4,4v16c0,1.1,0.9,2,2,2h12c1.1,0,2-0.9,2-2V8.83 C20,8.3,19.79,7.79,19.41,7.41z M15.74,18.74L15.74,18.74c-0.39,0.39-1.02,0.39-1.41,0l-1.18-1.18c-1.33,0.71-3.01,0.53-4.13-0.59 c-1.52-1.52-1.35-4.08,0.5-5.37c1.16-0.81,2.78-0.81,3.95,0c1.55,1.08,1.9,3.04,1.09,4.55l1.18,1.18 C16.13,17.72,16.13,18.35,15.74,18.74z M14,9c-0.55,0-1-0.45-1-1V3.5L18.5,9H14z"/><circle cx="11.5" cy="14.5" r="1.5"/></g></g>
  </svg>
</template>
        