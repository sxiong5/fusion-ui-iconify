
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MarkChatReadFilled',
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
    <g><rect fill="none" height="24" width="24" x="0"/><path d="M17.34,20l-3.54-3.54l1.41-1.41l2.12,2.12l4.24-4.24L23,14.34L17.34,20z M12,17c0-3.87,3.13-7,7-7c1.08,0,2.09,0.25,3,0.68 V4c0-1.1-0.9-2-2-2H4C2.9,2,2,2.9,2,4v18l4-4h6v0c0-0.17,0.01-0.33,0.03-0.5C12.01,17.34,12,17.17,12,17z"/></g>
  </svg>
</template>
        