
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'LightModeSharp',
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
    <rect fill="none" height="24" width="24"/><path d="M12,7c-2.76,0-5,2.24-5,5s2.24,5,5,5s5-2.24,5-5S14.76,7,12,7L12,7z M11,1v4h2V1L11,1z M11,19v4h2v-4L11,19z M23,11l-4,0v2 l4,0V11z M5,11l-4,0l0,2l4,0L5,11z M16.24,17.66l2.47,2.47l1.41-1.41l-2.47-2.47L16.24,17.66z M3.87,5.28l2.47,2.47l1.41-1.41 L5.28,3.87L3.87,5.28z M6.34,16.24l-2.47,2.47l1.41,1.41l2.47-2.47L6.34,16.24z M18.72,3.87l-2.47,2.47l1.41,1.41l2.47-2.47 L18.72,3.87z"/>
  </svg>
</template>
        