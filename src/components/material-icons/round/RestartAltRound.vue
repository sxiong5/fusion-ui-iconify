
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'RestartAltRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M12,5V3.21c0-0.45-0.54-0.67-0.85-0.35L8.35,5.65c-0.2,0.2-0.2,0.51,0,0.71l2.79,2.79C11.46,9.46,12,9.24,12,8.79V7 c3.31,0,6,2.69,6,6c0,2.72-1.83,5.02-4.31,5.75C13.27,18.87,13,19.27,13,19.7v0c0,0.65,0.62,1.16,1.25,0.97 C17.57,19.7,20,16.64,20,13C20,8.58,16.42,5,12,5z"/><path d="M6,13c0-1.34,0.44-2.58,1.19-3.59c0.3-0.4,0.26-0.95-0.09-1.31l0,0C6.68,7.68,5.96,7.72,5.6,8.2C4.6,9.54,4,11.2,4,13 c0,3.64,2.43,6.7,5.75,7.67C10.38,20.86,11,20.35,11,19.7v0c0-0.43-0.27-0.83-0.69-0.95C7.83,18.02,6,15.72,6,13z"/></g></g>
  </svg>
</template>
        