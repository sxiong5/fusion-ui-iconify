
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NoPhotographySharp',
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
    <g><rect fill="none" height="24" width="24"/><path d="M10.94,8.12L7.48,4.66L9,3h6l1.83,2H22v14.17l-5.12-5.12C16.96,13.71,17,13.36,17,13c0-2.76-2.24-5-5-5 C11.64,8,11.29,8.04,10.94,8.12z M20.49,23.31L18.17,21H2V5h0.17L0.69,3.51L2.1,2.1L21,21l0.9,0.9L20.49,23.31z M14.49,17.32 l-1.5-1.5C12.67,15.92,12.35,16,12,16c-1.66,0-3-1.34-3-3c0-0.35,0.08-0.67,0.19-0.98l-1.5-1.5C7.25,11.24,7,12.09,7,13 c0,2.76,2.24,5,5,5C12.91,18,13.76,17.75,14.49,17.32z"/></g>
  </svg>
</template>
        