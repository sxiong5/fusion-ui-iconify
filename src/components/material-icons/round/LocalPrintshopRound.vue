
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'LocalPrintshopRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M18,7V4c0-0.55-0.45-1-1-1H7C6.45,3,6,3.45,6,4v3H18z"/><path d="M19,8H5c-1.66,0-3,1.34-3,3v5c0,0.55,0.45,1,1,1h3v2c0,1.1,0.9,2,2,2h8c1.1,0,2-0.9,2-2v-2h3c0.55,0,1-0.45,1-1v-5 C22,9.34,20.66,8,19,8z M16,19H8v-4h8V19z M18,12.5c-0.55,0-1-0.45-1-1s0.45-1,1-1s1,0.45,1,1S18.55,12.5,18,12.5z"/></g></g>
  </svg>
</template>
        