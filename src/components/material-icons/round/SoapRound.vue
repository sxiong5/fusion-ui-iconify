
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SoapRound',
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
    <g><rect fill="none" height="24" width="24"/><path d="M14.25,6C14.66,6,15,6.34,15,6.75S14.66,7.5,14.25,7.5S13.5,7.16,13.5,6.75S13.84,6,14.25,6 M14.25,4.5 C13.01,4.5,12,5.51,12,6.75S13.01,9,14.25,9s2.25-1.01,2.25-2.25S15.49,4.5,14.25,4.5L14.25,4.5z M20,5.5c0.28,0,0.5,0.22,0.5,0.5 S20.28,6.5,20,6.5S19.5,6.28,19.5,6S19.72,5.5,20,5.5 M20,4c-1.1,0-2,0.9-2,2s0.9,2,2,2s2-0.9,2-2S21.1,4,20,4L20,4z M18,2.5 C18,3.33,17.33,4,16.5,4C15.67,4,15,3.33,15,2.5S15.67,1,16.5,1C17.33,1,18,1.67,18,2.5z M1.94,11.79C1.34,12.35,1,13.14,1,13.97 V20c0,1.66,1.34,3,3,3l13.68,0c0.65,0,1.25-0.47,1.32-1.12c0.08-0.75-0.51-1.38-1.24-1.38H12.5c-0.28,0-0.5-0.22-0.5-0.5v0 c0-0.28,0.22-0.5,0.5-0.5l7.18,0c0.65,0,1.25-0.47,1.32-1.12c0.08-0.75-0.51-1.38-1.24-1.38H12.5c-0.28,0-0.5-0.22-0.5-0.5l0,0 c0-0.28,0.22-0.5,0.5-0.5l8.18,0c0.65,0,1.25-0.47,1.32-1.12c0.08-0.75-0.51-1.38-1.24-1.38H12.5c-0.28,0-0.5-0.22-0.5-0.5v0 c0-0.28,0.22-0.5,0.5-0.5l6.18,0c0.65,0,1.25-0.47,1.32-1.12c0.08-0.75-0.51-1.38-1.24-1.38H8.86l1.49-2.61 c0.09-0.16,0.14-0.33,0.14-0.53c0-0.26-0.09-0.5-0.26-0.7L9.81,5.71C9.43,5.32,8.8,5.3,8.4,5.68L1.94,11.79z"/></g>
  </svg>
</template>
        