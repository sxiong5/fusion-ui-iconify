
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TireRepairFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M18,7c0,0.55,0.45,1,1,1c0.28,0,0.53-0.11,0.71-0.29c0.4-0.4,1.04-2.46,1.04-2.46s-2.06,0.64-2.46,1.04 C18.11,6.47,18,6.72,18,7z"/><path d="M19,2c-2.76,0-5,2.24-5,5c0,2.05,1.23,3.81,3,4.58V13h1v5c0,0.55-0.45,1-1,1s-1-0.45-1-1v-2c0-1.65-1.35-3-3-3 c-0.35,0-0.69,0.06-1,0.17V5c0-1.1-0.9-2-2-2H4C2.9,3,2,3.9,2,5v14c0,1.1,0.9,2,2,2h6c1.1,0,2-0.9,2-2v-3c0-0.55,0.45-1,1-1 s1,0.45,1,1v2c0,1.65,1.35,3,3,3s3-1.35,3-3v-5h1v-1.42c1.77-0.77,3-2.53,3-4.58C24,4.24,21.76,2,19,2z M6,19.5l-2-2v-2.83l2,2 V19.5z M6,14.5l-2-2V9.67l2,2V14.5z M6,9.5l-2-2V4.67l2,2V9.5z M10,17.5l-2,2v-2.83l2-2V17.5z M10,12.5l-2,2v-2.83l2-2V12.5z M10,7.5l-2,2V6.67l2-2V7.5z M19,10c-1.66,0-3-1.34-3-3s1.34-3,3-3s3,1.34,3,3S20.66,10,19,10z"/></g></g>
  </svg>
</template>
        