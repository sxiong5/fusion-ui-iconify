
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MosqueFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M7,8h10c0.29,0,0.57,0.06,0.84,0.13C17.93,7.8,18,7.46,18,7.09c0-1.31-0.65-2.53-1.74-3.25L12,1L7.74,3.84 C6.65,4.56,6,5.78,6,7.09C6,7.46,6.07,7.8,6.16,8.13C6.43,8.06,6.71,8,7,8z"/><path d="M24,7c0-1.1-2-3-2-3s-2,1.9-2,3c0,0.74,0.4,1.38,1,1.72V13h-2v-2c0-1.1-0.9-2-2-2H7c-1.1,0-2,0.9-2,2v2H3V8.72 C3.6,8.38,4,7.74,4,7c0-1.1-2-3-2-3S0,5.9,0,7c0,0.74,0.4,1.38,1,1.72V21h9v-4c0-1.1,0.9-2,2-2s2,0.9,2,2v4h9V8.72 C23.6,8.38,24,7.74,24,7z"/></g></g>
  </svg>
</template>
        