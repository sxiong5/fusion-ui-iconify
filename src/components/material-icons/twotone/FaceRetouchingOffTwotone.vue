
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FaceRetouchingOffTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M12,4c-0.46,0-0.91,0.05-1.34,0.12C12.06,6.44,14.6,8,17.5,8c0.46,0,0.91-0.05,1.34-0.12 C17.44,5.56,14.9,4,12,4z M4.42,9.47C5.09,9.09,5.7,8.61,6.23,8.06L5.51,7.34C5.05,7.99,4.68,8.7,4.42,9.47z" opacity=".3"/><path d="M9,14.25c0.69,0,1.25-0.56,1.25-1.25S9.69,11.75,9,11.75S7.75,12.31,7.75,13S8.31,14.25,9,14.25z M17.5,10 c0.75,0,1.47-0.09,2.17-0.24C19.88,10.47,20,11.22,20,12c0,1.22-0.28,2.37-0.77,3.4l1.49,1.49C21.53,15.44,22,13.78,22,12 c0-5.52-4.48-10-10-10c-1.78,0-3.44,0.47-4.89,1.28l5.33,5.33C13.93,9.49,15.65,10,17.5,10z M10.66,4.12C11.09,4.05,11.54,4,12,4 c2.9,0,5.44,1.56,6.84,3.88C18.41,7.95,17.96,8,17.5,8C14.6,8,12.06,6.44,10.66,4.12z M1.89,3.72l2.19,2.19C2.78,7.6,2,9.71,2,12 c0,5.52,4.48,10,10,10c2.29,0,4.4-0.78,6.09-2.08l2.19,2.19l1.41-1.41L3.31,2.31L1.89,3.72z M16.66,18.49 C15.35,19.44,13.74,20,12,20c-4.41,0-8-3.59-8-8c0-0.05,0.01-0.1,0-0.14c1.39-0.52,2.63-1.35,3.64-2.39L16.66,18.49z M5.51,7.34 l0.72,0.72C5.7,8.61,5.09,9.09,4.42,9.47C4.68,8.7,5.05,7.99,5.51,7.34z"/></g></g>
  </svg>
</template>
        