
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MosqueOutlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M24,7c0-1.1-2-3-2-3s-2,1.9-2,3c0,0.74,0.4,1.38,1,1.72V13h-2v-2c0-0.95-0.66-1.74-1.55-1.94C17.79,8.48,18,7.81,18,7.09 c0-1.31-0.65-2.53-1.74-3.25L12,1L7.74,3.84C6.65,4.56,6,5.78,6,7.09c0,0.72,0.21,1.39,0.55,1.96C5.66,9.26,5,10.05,5,11v2H3V8.72 C3.6,8.38,4,7.74,4,7c0-1.1-2-3-2-3S0,5.9,0,7c0,0.74,0.4,1.38,1,1.72V21h10v-4c0-0.55,0.45-1,1-1s1,0.45,1,1v4h10V8.72 C23.6,8.38,24,7.74,24,7z M8.85,5.5L12,3.4l3.15,2.1C15.68,5.86,16,6.45,16,7.09C16,8.14,15.14,9,14.09,9H9.91 C8.86,9,8,8.14,8,7.09C8,6.45,8.32,5.86,8.85,5.5z M21,19h-6v-2c0-1.65-1.35-3-3-3c-1.65,0-3,1.35-3,3v2H3v-4h4v-4h10v4h4V19z"/></g>
  </svg>
</template>
        