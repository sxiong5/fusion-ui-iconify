
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AirplanemodeActiveRound',
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
    <g><path d="M21.48,13.7L13.5,9V3.5C13.5,2.67,12.83,2,12,2c-0.83,0-1.5,0.67-1.5,1.5V9l-7.98,4.7C2.2,13.88,2,14.23,2,14.6 c0,0.7,0.67,1.2,1.34,1.01l7.16-2.1V19l-2.26,1.35C8.09,20.44,8,20.61,8,20.78l0,0.5h0v0.08c0,0.33,0.31,0.57,0.62,0.49l2.92-0.73 L12,21l0.38,0.09c0,0,0,0,0,0l0.42,0.11l1.9,0.48l0,0l0.67,0.17c0.32,0.08,0.62-0.16,0.62-0.49v-0.37c0,0,0,0,0,0v-0.21 c0-0.18-0.09-0.34-0.24-0.43L13.5,19v-5.5l7.16,2.1C21.33,15.8,22,15.3,22,14.6C22,14.23,21.8,13.88,21.48,13.7z"/><path d="M0,0h24v24H0V0z" fill="none"/></g>
  </svg>
</template>
        