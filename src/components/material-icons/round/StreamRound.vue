
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'StreamRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><circle cx="20" cy="12" r="2"/><circle cx="4" cy="12" r="2"/><circle cx="12" cy="20" r="2"/><path d="M7.89,14.65l-2.94,2.93c-0.39,0.39-0.39,1.02,0,1.41s1.02,0.39,1.41,0l2.94-2.93c0.39-0.38,0.39-1.02,0-1.41 C8.91,14.26,8.28,14.26,7.89,14.65z"/><path d="M6.41,4.94C6.02,4.55,5.39,4.55,5,4.94C4.61,5.33,4.61,5.96,5,6.35l2.93,2.94c0.39,0.39,1.02,0.39,1.42,0 C9.73,8.9,9.73,8.27,9.34,7.88L6.41,4.94z"/><path d="M16.12,14.65c-0.39-0.39-1.02-0.39-1.42,0c-0.39,0.39-0.39,1.02,0,1.41L17.64,19c0.39,0.39,1.02,0.39,1.41,0 s0.39-1.02,0-1.41L16.12,14.65z"/><path d="M16.06,9.33l2.99-2.98c0.39-0.4,0.39-1.03,0-1.42c-0.39-0.39-1.02-0.39-1.41,0l-2.99,2.98c-0.39,0.39-0.39,1.02,0,1.42 C15.04,9.72,15.67,9.72,16.06,9.33z"/><circle cx="12" cy="4" r="2"/></g></g>
  </svg>
</template>
        