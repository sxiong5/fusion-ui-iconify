
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NoStrollerSharp',
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
    <g><rect fill="none" height="24" width="24"/><path d="M10.91,8.08L6.53,3.7C7.6,3.25,8.77,3,10,3c1.56,0,3.03,0.4,4.3,1.1L10.91,8.08z M21.19,21.19l-4.78-4.78l-5.75-5.75 L2.81,2.81L1.39,4.22l7.97,7.97L5.27,17h8.9l1.13,1.13c-0.88,0.33-1.47,1.25-1.26,2.28c0.15,0.76,0.78,1.39,1.54,1.54 c1.03,0.21,1.95-0.38,2.28-1.26l1.91,1.91L21.19,21.19z M6,18c-1.1,0-2,0.9-2,2s0.9,2,2,2s2-0.9,2-2S7.1,18,6,18z M17,6.27 C17.58,5.59,17.97,5,18.65,5C19.42,5,20,5.66,20,6.48V7h2V6.48C22,4.56,20.52,3,18.65,3c-1.66,0-2.54,1.27-3.18,2.03l-3.5,4.11 L17,14.17V6.27z"/></g>
  </svg>
</template>
        