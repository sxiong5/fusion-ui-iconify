
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CountertopsRound',
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
    <rect fill="none" height="24" width="24"/><path d="M18,10l0-2.83c0-1.62-1.22-3.08-2.84-3.17c-1.21-0.06-2.27,0.59-2.8,1.57C12.01,6.22,12.53,7,13.27,7h0.01 c0.34,0,0.68-0.16,0.84-0.46C14.28,6.22,14.62,6,15,6c0.55,0,1,0.45,1,1v3H8c1.1,0,2-0.9,2-2V5c0-0.55-0.45-1-1-1H5 C4.45,4,4,4.45,4,5v3c0,1.1,0.9,2,2,2H3c-0.55,0-1,0.45-1,1v0c0,0.55,0.45,1,1,1h1v7c0,0.55,0.45,1,1,1h14c0.55,0,1-0.45,1-1v-7h1 c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1H18z M13,18h-2v-6h2V18z"/>
  </svg>
</template>
        