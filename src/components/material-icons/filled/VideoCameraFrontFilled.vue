
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'VideoCameraFrontFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M18,10.48V6c0-1.1-0.9-2-2-2H4C2.9,4,2,4.9,2,6v12c0,1.1,0.9,2,2,2h12c1.1,0,2-0.9,2-2v-4.48l4,3.98v-11L18,10.48z M10,8 c1.1,0,2,0.9,2,2s-0.9,2-2,2s-2-0.9-2-2S8.9,8,10,8z M14,16H6v-0.57c0-0.81,0.48-1.53,1.22-1.85C8.07,13.21,9.01,13,10,13 c0.99,0,1.93,0.21,2.78,0.58C13.52,13.9,14,14.62,14,15.43V16z"/></g>
  </svg>
</template>
        