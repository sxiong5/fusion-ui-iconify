
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DataExplorationRound',
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
    <rect fill="none" height="24" width="24"/><path d="M22,12c0-5.52-4.48-10-10-10S2,6.48,2,12c0,1.33,0.26,2.61,0.74,3.77l4.61-4.62c0.37-0.37,0.95-0.39,1.35-0.06l2.6,2.19 L14.58,10H14c-0.55,0-1-0.45-1-1c0-0.55,0.45-1,1-1h3c0.55,0,1,0.45,1,1v3c0,0.55-0.45,1-1,1s-1-0.45-1-1v-0.58l-3.94,3.93 c-0.37,0.37-0.96,0.39-1.35,0.05l-2.59-2.19l-4.4,4.4C5.52,20.26,8.56,22,12,22h8c1.1,0,2-0.9,2-2V12z M19.5,20.5 c-0.55,0-1-0.45-1-1s0.45-1,1-1s1,0.45,1,1S20.05,20.5,19.5,20.5z"/>
  </svg>
</template>
        