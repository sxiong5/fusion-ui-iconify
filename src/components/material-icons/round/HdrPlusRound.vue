
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'HdrPlusRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><rect height="1" width="2" x="8.5" y="14.5"/><rect height="3" width="1.5" x="14.5" y="7.5"/><path d="M12,2C6.48,2,2,6.48,2,12s4.48,10,10,10s10-4.48,10-10S17.52,2,12,2z M12,15.5c0,0.6-0.4,1.1-0.9,1.4l0.49,1.13 c0.2,0.46-0.14,0.97-0.64,0.97h0c-0.27,0-0.52-0.16-0.63-0.41L9.6,17H8.5v1.31C8.5,18.69,8.19,19,7.81,19H7.69 C7.31,19,7,18.69,7,18.31V14c0-0.55,0.45-1,1-1h2.5c0.82,0,1.5,0.68,1.5,1.5V15.5z M11.25,12L11.25,12 c-0.41,0-0.75-0.34-0.75-0.75V9.5h-2v1.75C8.5,11.66,8.16,12,7.75,12h0C7.34,12,7,11.66,7,11.25v-4.5C7,6.34,7.34,6,7.75,6h0 C8.16,6,8.5,6.34,8.5,6.75V8h2V6.75C10.5,6.34,10.84,6,11.25,6h0C11.66,6,12,6.34,12,6.75v4.5C12,11.66,11.66,12,11.25,12z M16.75,16H16v0.75c0,0.41-0.34,0.75-0.75,0.75h0c-0.41,0-0.75-0.34-0.75-0.75V16h-0.75C13.34,16,13,15.66,13,15.25v0 c0-0.41,0.34-0.75,0.75-0.75h0.75v-0.75c0-0.41,0.34-0.75,0.75-0.75h0c0.41,0,0.75,0.34,0.75,0.75v0.74h0.75 c0.41,0,0.75,0.34,0.75,0.75v0.01C17.5,15.66,17.16,16,16.75,16z M17.5,10.5c0,0.82-0.67,1.5-1.5,1.5h-2.5 c-0.28,0-0.5-0.22-0.5-0.5v-5C13,6.22,13.22,6,13.5,6H16c0.83,0,1.5,0.68,1.5,1.5V10.5z"/></g></g>
  </svg>
</template>
        