
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AddLocationAltRound',
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
    <g><rect fill="none" height="24" width="24" y="0"/></g><g><path d="M19,0c0.55,0,1,0.45,1,1v2h2c0.55,0,1,0.45,1,1s-0.45,1-1,1h-2v2c0,0.55-0.45,1-1,1s-1-0.45-1-1V5h-2c-0.55,0-1-0.45-1-1 s0.45-1,1-1h2V1C18,0.45,18.45,0,19,0z M12,12c1.1,0,2-0.9,2-2s-0.9-2-2-2s-2,0.9-2,2S10.9,12,12,12z M14.72,2.47 C14.28,2.83,14,3.38,14,4c0,1.1,0.9,2,2,2h1v1c0,1.1,0.9,2,2,2c0.32,0,0.62-0.08,0.89-0.21C19.96,9.24,20,9.71,20,10.2 c0,3.18-2.45,6.92-7.34,11.23c-0.38,0.33-0.95,0.33-1.33,0C6.45,17.12,4,13.38,4,10.2C4,5.22,7.8,2,12,2 C12.94,2,13.86,2.16,14.72,2.47z"/></g>
  </svg>
</template>
        