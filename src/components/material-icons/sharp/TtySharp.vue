
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TtySharp',
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
    <g><rect fill="none" height="24" width="24" x="0"/><path d="M20,15v6c-3.28,0-6.35-0.89-9-2.43C8.27,16.99,6.01,14.73,4.43,12C2.89,9.35,2,6.28,2,3h6l1,5l-2.9,2.9 c1.43,2.5,3.5,4.57,6,6L15,14L20,15z M14,6h2V4h-2V6z M13,9h2V7h-2V9z M11,6h2V4h-2V6z M18,7h-2v2h2V7z M19,4h-2v2h2V4z M21,7h-2v2 h2V7z M22,4h-2v2h2V4z M14,12h2v-2h-2V12z M11,12h2v-2h-2V12z M19,10h-2v2h2V10z M22,10h-2v2h2V10z"/></g>
  </svg>
</template>
        