
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'HandshakeSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M10.59,5.95l-7.05,7.04L0.7,10.3l8.55-8.55l7.95,7.95l-1.42,1.42L10.59,5.95z M23.24,10.24l-8.49-8.49l-2.06,2.06l5.9,5.88 l-2.83,2.83l-5.17-5.17l-6.27,6.27l1.42,1.41l5.32-5.32l0.71,0.71l-5.32,5.32l1.42,1.41l5.32-5.32l0.71,0.71l-5.32,5.32l1.41,1.41 l5.32-5.32l0.71,0.71L10.68,20l1.41,1.41L23.24,10.24z"/></g>
  </svg>
</template>
        