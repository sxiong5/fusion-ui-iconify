
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'Groups3Sharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M16.24,13.65c-1.17-0.52-2.61-0.9-4.24-0.9c-1.63,0-3.07,0.39-4.24,0.9C6.68,14.13,6,15.21,6,16.39V18h12v-1.61 C18,15.21,17.32,14.13,16.24,13.65z"/><path d="M1.22,14.58C0.48,14.9,0,15.62,0,16.43V18l4.5,0v-1.61c0-0.83,0.23-1.61,0.63-2.29C4.76,14.04,4.39,14,4,14 C3.01,14,2.07,14.21,1.22,14.58z"/><path d="M22.78,14.58C21.93,14.21,20.99,14,20,14c-0.39,0-0.76,0.04-1.13,0.1c0.4,0.68,0.63,1.46,0.63,2.29V18l4.5,0v-1.57 C24,15.62,23.52,14.9,22.78,14.58z"/><path d="M12,12c1.66,0,3-1.34,3-3c0-1.66-1.34-3-3-3S9,7.34,9,9C9,10.66,10.34,12,12,12z"/><rect height="3.54" transform="matrix(0.7071 -0.7071 0.7071 0.7071 -6.6066 6.0503)" width="3.54" x="2.23" y="9.23"/><polygon points="20,9 17.5,13 22.5,13"/></g></g>
  </svg>
</template>
        