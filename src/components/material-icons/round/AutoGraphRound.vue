
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AutoGraphRound',
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
    <rect fill="none" height="24" width="24"/><g><path d="M14.06,9.94L13,9.45c-0.39-0.18-0.39-0.73,0-0.91l1.06-0.49L14.55,7c0.18-0.39,0.73-0.39,0.91,0l0.49,1.06L17,8.55 c0.39,0.18,0.39,0.73,0,0.91l-1.06,0.49L15.45,11c-0.18,0.39-0.73,0.39-0.91,0L14.06,9.94z M4.45,13l0.49-1.06L6,11.45 c0.39-0.18,0.39-0.73,0-0.91l-1.06-0.49L4.45,9C4.28,8.61,3.72,8.61,3.55,9l-0.49,1.06L2,10.55c-0.39,0.18-0.39,0.73,0,0.91 l1.06,0.49L3.55,13C3.72,13.39,4.28,13.39,4.45,13z M8.96,7.99l0.63-1.4l1.4-0.63c0.39-0.18,0.39-0.73,0-0.91l-1.4-0.63l-0.63-1.4 c-0.18-0.39-0.73-0.39-0.91,0l-0.63,1.4l-1.4,0.63c-0.39,0.18-0.39,0.73,0,0.91l1.4,0.63l0.63,1.4C8.22,8.38,8.78,8.38,8.96,7.99z M22.34,8.27c-0.4-0.4-1.07-0.39-1.45,0.04l-6.39,7.18l-3.29-3.29c-0.39-0.39-1.02-0.39-1.41,0l-6.04,6.05 c-0.41,0.41-0.41,1.09,0,1.5c0.41,0.41,1.09,0.41,1.5,0l5.25-5.26l3.25,3.25c0.41,0.41,1.07,0.39,1.45-0.04l7.17-8.07 C22.73,9.24,22.71,8.64,22.34,8.27z"/></g>
  </svg>
</template>
        