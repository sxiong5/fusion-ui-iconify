
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TranscribeSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M17.93,16l1.63-1.63c-2.77-3.02-2.77-7.56,0-10.74L17.93,2C14.03,5.89,14.02,11.95,17.93,16z M22.92,10.95 c-0.84-1.18-0.84-2.71,0-3.89l-1.68-1.69c-2.02,2.02-2.02,5.07,0,7.27L22.92,10.95z M9,13c2.21,0,4-1.79,4-4c0-2.21-1.79-4-4-4 S5,6.79,5,9C5,11.21,6.79,13,9,13z M15.39,15.56C13.71,14.7,11.53,14,9,14c-2.53,0-4.71,0.7-6.39,1.56C1.61,16.07,1,17.1,1,18.22 V21h16v-2.78C17,17.1,16.39,16.07,15.39,15.56z"/></g>
  </svg>
</template>
        