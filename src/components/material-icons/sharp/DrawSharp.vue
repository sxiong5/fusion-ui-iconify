
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DrawSharp',
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
    <rect fill="none" height="24" width="24"/><path d="M18.85,10.39l2.48-2.48l-4.24-4.24l-2.48,2.48L18.85,10.39z M13.19,7.56L4,16.76V21h4.24l9.19-9.19L13.19,7.56z M19,17.5 c0,2.19-2.54,3.5-5,3.5c-0.48,0-1-0.07-1-0.07c0-0.34,0-2.03,0-2.03S13.46,19,14,19c1.54,0,3-0.73,3-1.5c0-0.47-0.48-0.87-1.23-1.2 l1.48-1.48C18.32,15.45,19,16.29,19,17.5z M4.58,13.35C3.61,12.79,3,12.06,3,11c0-1.8,1.89-2.63,3.56-3.36C7.59,7.18,9,6.56,9,6 c0-0.41-0.78-1-2-1C5.76,5,5,5.61,5,6H3c0-1.65,1.7-3,4-3c2.24,0,4,1.32,4,3c0,1.87-1.93,2.72-3.64,3.47C6.42,9.88,5,10.5,5,11 c0,0.31,0.43,0.6,1.07,0.86L4.58,13.35z"/>
  </svg>
</template>
        