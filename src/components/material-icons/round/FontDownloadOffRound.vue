
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FontDownloadOffRound',
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
    <rect fill="none" height="24" width="24"/><path d="M12.58,9.75l-0.87-0.87l0.23-0.66h0.1L12.58,9.75z M10.35,7.52L10.55,7c0.23-0.6,0.8-1,1.45-1s1.22,0.4,1.45,1l2.17,5.79 L22,19.17V4c0-1.1-0.9-2-2-2H4.83L10.35,7.52z M21.19,22.61L21.19,22.61c-0.39,0.39-1.02,0.39-1.41,0L19.17,22H4c-1.1,0-2-0.9-2-2 V4.83L1.39,4.22C1,3.83,1,3.2,1.39,2.81l0,0c0.39-0.39,1.02-0.39,1.41,0l18.38,18.38C21.58,21.58,21.58,22.22,21.19,22.61z M12.1,14.93l-3.3-3.3L6.9,16.7C6.67,17.33,7.13,18,7.8,18h0.01c0.41,0,0.77-0.26,0.9-0.64l0.86-2.43H12.1z"/>
  </svg>
</template>
        