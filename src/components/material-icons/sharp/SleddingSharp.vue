
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SleddingSharp',
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
    <rect fill="none" height="24" width="24"/><path d="M14,4.5c0,1.1-0.9,2-2,2s-2-0.9-2-2s0.9-2,2-2S14,3.4,14,4.5z M17.22,17.9l1.93,0.63l-0.46,1.43l-3.32-1.08L14.9,20.3 l3.32,1.08l0,0c1.31,0.43,2.72-0.29,3.15-1.61c0.43-1.31-0.29-2.72-1.61-3.15l0.46-1.43c2.1,0.68,3.25,2.94,2.57,5.04 c-0.68,2.1-2.94,3.25-5.04,2.57h0L1,17.36l0.46-1.43l3.93,1.28l0.46-1.43L1.93,14.5l0.46-1.43L4,13.6V9.5l5.47-2.35 c0.39-0.17,0.84-0.21,1.28-0.07c0.95,0.31,1.46,1.32,1.16,2.27l-1.05,3.24L14.5,12L17.22,17.9z M6,14.25l0.48,0.16l0.75-2.31 L7.92,10L6,10.82V14.25z M13.94,18.41l-6.66-2.16l-0.46,1.43l6.66,2.16L13.94,18.41z M14.63,17.05l-1.18-2.56l-3.97,0.89 L14.63,17.05z"/>
  </svg>
</template>
        