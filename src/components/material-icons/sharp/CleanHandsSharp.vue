
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CleanHandsSharp',
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
    <rect fill="none" height="24" width="24"/><g><path d="M14.99,7l1.37-0.63L16.99,5l0.63,1.37L18.99,7l-1.37,0.63L16.99,9l-0.63-1.37L14.99,7z M20,14c1.1,0,2-0.9,2-2 c0-1.1-2-4-2-4s-2,2.9-2,4C18,13.1,18.9,14,20,14z M1,22h4V11H1V22z M9.24,9.5L15,11.65V11c0-2.42-1.72-4.44-4-4.9V4h2 c0.57,0,1.1,0.17,1.55,0.45l1.43-1.43C15.15,2.39,14.13,2,13,2c-1.48,0-5.5,0-5.5,0v2H9v2.11C7.22,6.48,5.8,7.79,5.25,9.5H9.24z M22,17h-9l-2.09-0.73l0.33-0.94L13,16h4l0-2l-8.03-3H7v9.02L14,22l8-3V17z"/></g>
  </svg>
</template>
        