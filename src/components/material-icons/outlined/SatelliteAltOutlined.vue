
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SatelliteAltOutlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M21,14l2,0c0,4.97-4.03,9-9,9l0-2C17.87,21,21,17.87,21,14z M14,17l0,2c2.76,0,5-2.24,5-5l-2,0C17,15.66,15.66,17,14,17z M18.26,0.59l3.54,3.54c0.78,0.78,0.78,2.05,0,2.83l-3.18,3.18c-0.78,0.78-2.05,0.78-2.83,0l-1.24-1.24L13.84,9.6l1.24,1.24 c0.78,0.78,0.78,2.05,0,2.83l-1.41,1.41c-0.78,0.78-2.05,0.78-2.83,0L9.6,13.84l-0.71,0.71l1.24,1.24c0.78,0.78,0.78,2.05,0,2.83 L6.95,21.8c-0.78,0.78-2.05,0.78-2.83,0l-3.54-3.54c-0.78-0.78-0.78-2.05,0-2.83l3.18-3.18c0.78-0.78,2.05-0.78,2.83,0l1.24,1.24 l0.71-0.71L7.3,11.55c-0.78-0.78-0.78-2.05,0-2.83L8.72,7.3c0.78-0.78,2.05-0.78,2.83,0l1.24,1.24l0.71-0.71L12.25,6.6 c-0.78-0.78-0.78-2.05,0-2.83l3.18-3.18C16.22-0.2,17.48-0.2,18.26,0.59z M3.06,15.79L2,16.85l3.54,3.54l1.06-1.06L3.06,15.79z M5.18,13.67l-1.06,1.06l3.54,3.54l1.06-1.06L5.18,13.67z M10.13,8.72l-1.41,1.41l3.54,3.54l1.41-1.41L10.13,8.72z M14.73,4.12 l-1.06,1.06l3.54,3.54l1.06-1.06L14.73,4.12z M16.85,2l-1.06,1.06l3.54,3.54l1.06-1.06L16.85,2z"/></g>
  </svg>
</template>
        