
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FestivalSharp',
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
    <g><rect fill="none" height="24" width="24" y="0"/></g><g><path d="M23,11V9c-6-2-11-7-11-7S7,7,1,9v2c0,1.49,0.93,2.75,2.24,3.26C3.2,16.76,2.92,19.69,2,22h5h10h5 c-0.92-2.31-1.2-5.24-1.24-7.74C22.07,13.75,23,12.49,23,11z M12,4.71c1.33,1.14,3.49,2.84,6.11,4.29H5.89 C8.51,7.55,10.67,5.85,12,4.71z M13,11h3c0,0.83-0.67,1.5-1.5,1.5S13,11.83,13,11z M9.5,12.5C8.67,12.5,8,11.83,8,11h3 C11,11.83,10.33,12.5,9.5,12.5z M6,11c0,0.83-0.67,1.5-1.5,1.5S3,11.83,3,11H6z M4.66,20c0.39-1.86,0.54-3.82,0.57-5.58 c0.68-0.15,1.29-0.49,1.76-0.98c0.25,0.25,0.54,0.45,0.85,0.62c-0.1,1.87-0.26,4-0.52,5.93H4.66z M9.35,20 c0.24-1.83,0.39-3.78,0.48-5.53c0.84-0.08,1.61-0.45,2.17-1.02c0.56,0.57,1.32,0.94,2.17,1.02c0.1,1.75,0.24,3.7,0.48,5.53H9.35z M16.67,20c-0.27-1.94-0.43-4.07-0.52-5.93c0.31-0.17,0.61-0.37,0.85-0.62c0.47,0.48,1.08,0.83,1.76,0.98 c0.03,1.76,0.18,3.72,0.57,5.58H16.67z M19.5,12.5c-0.83,0-1.5-0.67-1.5-1.5h3C21,11.83,20.33,12.5,19.5,12.5z"/></g>
  </svg>
</template>
        