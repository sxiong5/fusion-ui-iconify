
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ThumbDownOffAltRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M14.99,3H6C5.2,3,4.48,3.48,4.17,4.21l-3.26,7.61C0.06,13.8,1.51,16,3.66,16h5.65l-0.95,4.58 c-0.1,0.5,0.05,1.01,0.41,1.37c0.29,0.29,0.67,0.43,1.05,0.43c0.38,0,0.77-0.15,1.06-0.44l5.53-5.54 c0.37-0.37,0.58-0.88,0.58-1.41V5C16.99,3.9,16.09,3,14.99,3z M10.66,19.33l0.61-2.92l0.5-2.41H9.31H3.66 c-0.47,0-0.72-0.28-0.83-0.45c-0.11-0.17-0.27-0.51-0.08-0.95L6,5h8.99l0,9.99L10.66,19.33z"/><path d="M21,3c-1.1,0-2,0.9-2,2v8c0,1.1,0.9,2,2,2s2-0.9,2-2V5C23,3.9,22.1,3,21,3z"/></g></g>
  </svg>
</template>
        