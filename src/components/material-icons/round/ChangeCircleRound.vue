
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ChangeCircleRound',
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
    <rect fill="none" height="24" width="24"/><path d="M12,2C6.48,2,2,6.48,2,12c0,5.52,4.48,10,10,10s10-4.48,10-10C22,6.48,17.52,2,12,2z M12.91,18.15 c-0.31,0.31-0.85,0.09-0.85-0.35v-0.8c-0.02,0-0.04,0-0.06,0c-1.28,0-2.56-0.49-3.54-1.46c-1.43-1.43-1.81-3.52-1.14-5.3 c0.19-0.51,0.86-0.64,1.24-0.25l0,0c0.22,0.22,0.27,0.54,0.17,0.82c-0.46,1.24-0.2,2.68,0.8,3.68c0.7,0.7,1.62,1.03,2.54,1.01v-0.94 c0-0.45,0.54-0.67,0.85-0.35l1.62,1.62c0.2,0.2,0.2,0.51,0,0.71L12.91,18.15z M15.44,14.02L15.44,14.02 c-0.22-0.22-0.27-0.54-0.17-0.82c0.46-1.24,0.2-2.68-0.8-3.68c-0.7-0.7-1.62-1.04-2.53-1.02c0,0,0,0,0,0v0.94 c0,0.45-0.54,0.67-0.85,0.35L9.46,8.18c-0.2-0.2-0.2-0.51,0-0.71l1.62-1.62c0.31-0.31,0.85-0.09,0.85,0.35v0.81 c1.3-0.02,2.61,0.45,3.6,1.45c1.43,1.43,1.81,3.52,1.14,5.3C16.48,14.28,15.82,14.41,15.44,14.02z"/>
  </svg>
</template>
        