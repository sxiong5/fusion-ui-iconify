
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NumbersRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M20.68,9.27l0.01-0.06C20.85,8.59,20.39,8,19.76,8H17l0.7-2.79C17.85,4.59,17.39,4,16.76,4h0c-0.45,0-0.83,0.3-0.94,0.73 L15,8h-4l0.7-2.79C11.85,4.59,11.39,4,10.76,4h0c-0.45,0-0.83,0.3-0.94,0.73L9,8H5.76C5.31,8,4.92,8.3,4.82,8.73L4.8,8.79 C4.65,9.41,5.11,10,5.74,10H8.5l-1,4H4.26c-0.45,0-0.83,0.3-0.94,0.73L3.3,14.79C3.15,15.41,3.61,16,4.24,16H7l-0.7,2.79 C6.15,19.41,6.61,20,7.24,20h0c0.45,0,0.83-0.3,0.94-0.73L9,16h4l-0.7,2.79C12.15,19.41,12.61,20,13.24,20h0 c0.45,0,0.83-0.3,0.94-0.73L15,16h3.24c0.45,0,0.83-0.3,0.94-0.73l0.01-0.06c0.15-0.61-0.31-1.21-0.94-1.21H15.5l1-4h3.24 C20.19,10,20.58,9.7,20.68,9.27z M13.5,14h-4l1-4h4L13.5,14z"/></g>
  </svg>
</template>
        