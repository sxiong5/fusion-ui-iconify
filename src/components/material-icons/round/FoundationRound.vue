
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FoundationRound',
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
    <rect fill="none" height="24" width="24"/><path d="M19,12h1.7c0.46,0,0.68-0.57,0.33-0.87L12.67,3.6c-0.38-0.34-0.96-0.34-1.34,0l-8.36,7.53C2.63,11.43,2.84,12,3.3,12H5v3H4 c-0.55,0-1,0.45-1,1v0c0,0.55,0.45,1,1,1h1v2c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v-2h4v2c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1 v-2h4v2c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v-2h1c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h-1V12z M7,15v-4.81l4-3.6V15H7z M13,15 V6.59l4,3.6V15H13z"/>
  </svg>
</template>
        