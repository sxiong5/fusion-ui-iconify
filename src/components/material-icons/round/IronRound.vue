
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'IronRound',
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
    <rect fill="none" height="24" width="24"/><path d="M8.27,10c0.34,0,0.68-0.16,0.84-0.47C9.28,9.22,9.62,9,10,9h4c0.55,0,1,0.45,1,1v1H6c-2.21,0-4,1.79-4,4v2 c0,0.55,0.45,1,1,1h13c0.55,0,1-0.45,1-1v-1c1.66,0,3-1.34,3-3V9c0-0.55,0.45-1,1-1h0c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h0 c-1.66,0-3,1.34-3,3v4c0,0.55-0.45,1-1,1v-4c0-1.66-1.34-3-3-3h-4C8.87,7,7.89,7.62,7.37,8.55C7.01,9.2,7.53,10,8.27,10z"/>
  </svg>
</template>
        