
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'VerticalDistributeRound',
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
    <rect fill="none" height="24" width="24"/><path d="M22,3L22,3c0,0.55-0.45,1-1,1H3C2.45,4,2,3.55,2,3v0c0-0.55,0.45-1,1-1h18C21.55,2,22,2.45,22,3z M7,12L7,12 c0,0.83,0.67,1.5,1.5,1.5h7c0.83,0,1.5-0.67,1.5-1.5v0c0-0.83-0.67-1.5-1.5-1.5h-7C7.67,10.5,7,11.17,7,12z M2,21L2,21 c0,0.55,0.45,1,1,1h18c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1H3C2.45,20,2,20.45,2,21z"/>
  </svg>
</template>
        