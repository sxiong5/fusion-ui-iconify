
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SportsHandballRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M14.27,6C13.72,6.95,14.05,8.18,15,8.73c0.95,0.55,2.18,0.22,2.73-0.73c0.55-0.95,0.22-2.18-0.73-2.73 C16.05,4.72,14.82,5.05,14.27,6z"/><path d="M15.84,10.41c0,0-1.63-0.94-2.6-1.5c-2.13-1.24-3.01-3.83-2.18-6.07c0.17-0.46-0.01-0.97-0.43-1.21 C10.1,1.33,9.41,1.56,9.2,2.13C8.25,4.64,8.85,7.48,10.66,9.4l-4.65,8.05c-0.28,0.48-0.11,1.09,0.37,1.37 c0.48,0.28,1.09,0.11,1.37-0.37l1-1.73l1.73,1l-2.5,4.33c-0.28,0.48-0.11,1.09,0.37,1.37c0.48,0.28,1.09,0.11,1.37-0.37 l5.79-10.02c0.98,1.34,1.26,3.12,0.66,4.72c-0.17,0.45,0.02,0.96,0.43,1.2c0.53,0.31,1.22,0.08,1.44-0.5 C19.01,15.83,18.45,12.61,15.84,10.41z"/><path d="M12.75,3.8c0.72,0.41,1.63,0.17,2.05-0.55c0.41-0.72,0.17-1.63-0.55-2.05c-0.72-0.41-1.63-0.17-2.05,0.55 C11.79,2.47,12.03,3.39,12.75,3.8z"/></g></g>
  </svg>
</template>
        