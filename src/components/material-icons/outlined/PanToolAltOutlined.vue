
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'PanToolAltOutlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M18.89,11.77l-3.8-1.67C14.96,10.04,14.81,10,14.65,10H14V5.5C14,4.12,12.88,3,11.5,3S9,4.12,9,5.5v8.15l-1.87-0.4 c-0.19-0.03-1.02-0.15-1.73,0.56L4,15.22l5.12,5.19C9.49,20.79,10,21,10.53,21h6.55c0.98,0,1.81-0.7,1.97-1.67l0.92-5.44 C20.12,13.03,19.68,12.17,18.89,11.77z M17.08,19h-6.55l-3.7-3.78L11,16.11V5.5C11,5.22,11.22,5,11.5,5S12,5.22,12,5.5v6.18h1.76 L18,13.56L17.08,19z"/></g>
  </svg>
</template>
        