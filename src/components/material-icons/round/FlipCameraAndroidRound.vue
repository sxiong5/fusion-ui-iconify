
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FlipCameraAndroidRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M9,12c0,1.66,1.34,3,3,3s3-1.34,3-3s-1.34-3-3-3S9,10.34,9,12z"/><path d="M8,9L8,9c0-0.55-0.45-1-1-1H5.09C6.47,5.61,9.05,4,12,4c3.49,0,6.45,2.24,7.54,5.36C19.68,9.75,20.07,10,20.48,10h0 c0.68,0,1.18-0.67,0.96-1.31C20.07,4.79,16.36,2,12,2C8.73,2,5.82,3.58,4,6.01V5c0-0.55-0.45-1-1-1h0C2.45,4,2,4.45,2,5v4 c0,0.55,0.45,1,1,1h4C7.55,10,8,9.55,8,9z"/><path d="M16,15L16,15c0,0.55,0.45,1,1,1h1.91c-1.38,2.39-3.96,4-6.91,4c-3.49,0-6.45-2.24-7.54-5.36C4.32,14.25,3.93,14,3.52,14h0 c-0.68,0-1.18,0.67-0.96,1.31C3.93,19.21,7.64,22,12,22c3.27,0,6.18-1.58,8-4.01V19c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v-4 c0-0.55-0.45-1-1-1h-4C16.45,14,16,14.45,16,15z"/></g></g>
  </svg>
</template>
        