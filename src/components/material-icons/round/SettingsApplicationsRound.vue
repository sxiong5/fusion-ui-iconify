
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SettingsApplicationsRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><circle cx="12" cy="12" r="2"/><path d="M19,3H5C3.89,3,3,3.9,3,5v14c0,1.1,0.89,2,2,2h14c1.11,0,2-0.9,2-2V5C21,3.9,20.11,3,19,3z M15.75,12 c0,0.22-0.03,0.42-0.06,0.63l0.84,0.73c0.18,0.16,0.22,0.42,0.1,0.63l-0.59,1.02c-0.12,0.21-0.37,0.3-0.59,0.22l-1.06-0.36 c-0.32,0.27-0.68,0.48-1.08,0.63l-0.22,1.09c-0.05,0.23-0.25,0.4-0.49,0.4h-1.18c-0.24,0-0.44-0.17-0.49-0.4l-0.22-1.09 c-0.4-0.15-0.76-0.36-1.08-0.63l-1.06,0.36c-0.23,0.08-0.47-0.02-0.59-0.22l-0.59-1.02c-0.12-0.21-0.08-0.47,0.1-0.63l0.84-0.73 C8.28,12.42,8.25,12.22,8.25,12s0.03-0.42,0.06-0.63l-0.84-0.73c-0.18-0.16-0.22-0.42-0.1-0.63l0.59-1.02 c0.12-0.21,0.37-0.3,0.59-0.22l1.06,0.36c0.32-0.27,0.68-0.48,1.08-0.63l0.22-1.09C10.97,7.17,11.17,7,11.41,7h1.18 c0.24,0,0.44,0.17,0.49,0.4l0.22,1.09c0.4,0.15,0.76,0.36,1.08,0.63l1.06-0.36c0.23-0.08,0.47,0.02,0.59,0.22l0.59,1.02 c0.12,0.21,0.08,0.47-0.1,0.63l-0.84,0.73C15.72,11.58,15.75,11.78,15.75,12z"/></g></g>
  </svg>
</template>
        