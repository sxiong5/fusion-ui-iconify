
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'VolcanoRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><g><path d="M16.49,8h-4.14c-0.82,0-1.55,0.5-1.86,1.26L9,13H7.3c-0.79,0-1.51,0.47-1.83,1.19l-2.22,5C2.66,20.51,3.63,22,5.08,22 h14.27c1.33,0,2.29-1.27,1.92-2.55l-2.86-10C18.17,8.59,17.38,8,16.49,8z"/></g><g><path d="M14,1L14,1c-0.55,0-1,0.45-1,1v2c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1V2C15,1.45,14.55,1,14,1z"/></g><g><path d="M19.66,3.34L19.66,3.34c-0.39-0.39-1.02-0.39-1.41,0l-1.41,1.41c-0.39,0.39-0.39,1.02,0,1.41v0 c0.39,0.39,1.02,0.39,1.41,0l1.41-1.41C20.05,4.37,20.05,3.73,19.66,3.34z"/></g><g><path d="M11.17,4.76L9.76,3.34c-0.39-0.39-1.02-0.39-1.41,0l0,0c-0.39,0.39-0.39,1.02,0,1.41l1.41,1.41 c0.39,0.39,1.02,0.39,1.41,0l0,0C11.56,5.78,11.56,5.15,11.17,4.76z"/></g></g></g>
  </svg>
</template>
        