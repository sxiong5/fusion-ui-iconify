
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SoupKitchenSharp',
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
    <rect fill="none" height="24" width="24"/><path d="M6.4,7C6.06,7.55,6,7.97,6,8.38C6,9.15,7,11,7,12c0,0.95-0.4,1.5-0.4,1.5H5.1c0,0,0.4-0.55,0.4-1.5c0-1-1-2.85-1-3.62 C4.5,7.97,4.56,7.55,4.9,7H6.4z M11.4,7C11.06,7.55,11,7.97,11,8.38C11,9.15,12,11,12,12c0,0.95-0.4,1.5-0.4,1.5h1.5 c0,0,0.4-0.55,0.4-1.5c0-1-1-2.85-1-3.62c0-0.41,0.06-0.83,0.4-1.38H11.4z M8.15,7c-0.34,0.55-0.4,0.97-0.4,1.38 c0,0.77,1,2.63,1,3.62c0,0.95-0.4,1.5-0.4,1.5h1.5c0,0,0.4-0.55,0.4-1.5c0-1-1-2.85-1-3.62c0-0.41,0.06-0.83,0.4-1.38H8.15z M21.47,6.5c0,0,0.13-1.06,0.13-1.5c0-1.65-1.35-3-3-3c-1.54,0-2.81,1.16-2.98,2.65L14.53,15l-11.6,0c-0.02,3.87,3.09,7,6.82,7 c3.48,0,6.34-2.73,6.71-6.23l1.15-10.87C17.66,4.39,18.08,4,18.6,4c0.55,0,1,0.45,1,1c0,0.3-0.1,1.25-0.1,1.25L21.47,6.5z"/>
  </svg>
</template>
        