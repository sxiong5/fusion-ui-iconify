
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'RawOnRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M6.5,9H4c-0.55,0-1,0.45-1,1v4.31C3,14.69,3.31,15,3.69,15h0.11c0.38,0,0.69-0.31,0.69-0.69V13h1.1l0.72,1.59 C6.43,14.84,6.68,15,6.95,15h0c0.5,0,0.83-0.51,0.64-0.97L7.1,12.9C7.6,12.6,8,12.1,8,11.5v-1C8,9.68,7.32,9,6.5,9z M6.5,11.5h-2 v-1h2V11.5z"/><path d="M11.5,9c-0.73,0-1.37,0.5-1.55,1.21L8.98,14.1C8.86,14.56,9.21,15,9.68,15h0c0.33,0,0.62-0.23,0.7-0.55l0.24-0.95h1.75 l0.23,0.95c0.08,0.32,0.37,0.55,0.71,0.55h0c0.47,0,0.82-0.44,0.71-0.9l-0.97-3.88C12.87,9.5,12.23,9,11.5,9L11.5,9z M11,12 l0.25-1h0.5L12,12H11z"/><path d="M19.84,9.55L19.24,12l-0.56-2.26C18.58,9.3,18.19,9,17.74,9l0,0c-0.45,0-0.84,0.3-0.94,0.74L16.24,12l-0.6-2.45 C15.56,9.23,15.27,9,14.93,9h0c-0.47,0-0.82,0.44-0.71,0.9l1.09,4.38C15.43,14.7,15.81,15,16.24,15l0,0c0.43,0,0.81-0.3,0.92-0.72 l0.58-2.32l0.58,2.32C18.43,14.7,18.81,15,19.24,15l0,0c0.43,0,0.81-0.3,0.92-0.72l1.09-4.38C21.37,9.44,21.02,9,20.55,9h0 C20.21,9,19.92,9.23,19.84,9.55z"/></g></g>
  </svg>
</template>
        