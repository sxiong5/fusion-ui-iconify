
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ContactlessRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M12,2C6.48,2,2,6.48,2,12c0,5.52,4.48,10,10,10s10-4.48,10-10C22,6.48,17.52,2,12,2z M8.75,13.68 c-0.13,0.43-0.62,0.63-1.02,0.45l0,0c-0.34-0.16-0.51-0.54-0.4-0.9c0.12-0.41,0.18-0.83,0.17-1.24c-0.01-0.41-0.06-0.8-0.17-1.18 c-0.1-0.36,0.06-0.75,0.4-0.9l0,0c0.42-0.19,0.91,0.04,1.04,0.49c0.15,0.51,0.22,1.03,0.23,1.57C9,12.53,8.92,13.11,8.75,13.68z M11.89,15.27c-0.17,0.41-0.67,0.57-1.06,0.35l0,0c-0.33-0.19-0.46-0.59-0.32-0.94c0.33-0.77,0.49-1.63,0.49-2.56 c0-0.96-0.18-1.89-0.53-2.78c-0.14-0.36,0.02-0.76,0.36-0.94l0,0c0.39-0.2,0.87-0.02,1.03,0.39c0.42,1.06,0.63,2.18,0.63,3.33 C12.51,13.25,12.3,14.31,11.89,15.27z M15,16.6c-0.17,0.4-0.64,0.58-1.02,0.39l0,0c-0.35-0.17-0.52-0.59-0.37-0.95 c0.59-1.39,0.89-2.75,0.89-4.06c0-1.31-0.3-2.65-0.88-4.01c-0.16-0.36,0.01-0.78,0.36-0.95C14.37,6.82,14.83,7,15,7.4 c0.66,1.54,1,3.08,1,4.58C16,13.48,15.66,15.04,15,16.6z"/></g>
  </svg>
</template>
        