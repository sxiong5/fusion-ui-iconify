
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AttachEmailTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M3,6l8,5l8-5v3h2V4c0-1.1-0.9-2-2-2H3C1.9,2,1.01,2.9,1.01,4L1,16c0,1.1,0.9,2,2,2h10v-2H3V6z M19,4l-8,5L3,4H19z"/><path d="M21,14v4c0,1.1-0.9,2-2,2s-2-0.9-2-2v-4.5c0-0.28,0.22-0.5,0.5-0.5s0.5,0.22,0.5,0.5V18h2v-4.5c0-1.38-1.12-2.5-2.5-2.5 S15,12.12,15,13.5V18c0,2.21,1.79,4,4,4s4-1.79,4-4v-4H21z"/></g></g>
  </svg>
</template>
        