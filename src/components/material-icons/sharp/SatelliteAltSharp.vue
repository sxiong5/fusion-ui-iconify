
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SatelliteAltSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M15.44,0.59l-3.18,3.18c-0.78,0.78-0.78,2.05,0,2.83l1.24,1.24l-0.71,0.71l-2.65-2.65l-4.24,4.24l2.65,2.65l-0.71,0.71 L6.6,12.25c-0.78-0.78-2.05-0.78-2.83,0l-3.18,3.18c-0.78,0.78-0.78,2.05,0,2.83l3.54,3.54c0.78,0.78,2.05,0.78,2.83,0l3.18-3.18 c0.78-0.78,0.78-2.05,0-2.83l-1.24-1.24l0.71-0.71l2.65,2.65l4.24-4.24L13.84,9.6l0.71-0.71l1.24,1.24c0.78,0.78,2.05,0.78,2.83,0 l3.18-3.18c0.78-0.78,0.78-2.05,0-2.83l-3.54-3.54C17.48-0.2,16.22-0.2,15.44,0.59z M6.6,19.32l-1.06,1.06L2,16.85l1.06-1.06 L6.6,19.32z M8.72,17.2l-1.06,1.06l-3.54-3.54l1.06-1.06L8.72,17.2z M18.26,7.66L17.2,8.72l-3.54-3.54l1.06-1.06L18.26,7.66z M20.38,5.54L19.32,6.6l-3.54-3.54L16.85,2L20.38,5.54z M21,14l2,0c0,4.97-4.03,9-9,9l0-2C17.87,21,21,17.87,21,14z M17,14l2,0 c0,2.76-2.24,5-5,5l0-2C15.66,17,17,15.66,17,14z"/></g></g>
  </svg>
</template>
        