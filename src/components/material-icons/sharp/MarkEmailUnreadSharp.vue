
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MarkEmailUnreadSharp',
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
    <g><rect fill="none" height="24" width="24" x="0"/><path d="M22,8.98V20H2V4h12.1C14.04,4.32,14,4.66,14,5c0,1.48,0.65,2.79,1.67,3.71L12,11L4,6v2l8,5l5.3-3.32 C17.84,9.88,18.4,10,19,10C20.13,10,21.16,9.61,22,8.98z M16,5c0,1.66,1.34,3,3,3s3-1.34,3-3s-1.34-3-3-3S16,3.34,16,5z"/></g>
  </svg>
</template>
        