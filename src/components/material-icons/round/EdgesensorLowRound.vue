
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'EdgesensorLowRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M3,7L3,7c0.55,0,1,0.45,1,1v5c0,0.55-0.45,1-1,1h0c-0.55,0-1-0.45-1-1V8C2,7.45,2.45,7,3,7z M21,10L21,10 c0.55,0,1,0.45,1,1v5c0,0.55-0.45,1-1,1h0c-0.55,0-1-0.45-1-1v-5C20,10.45,20.45,10,21,10z M16,2.01L8,2C6.9,2,6,2.9,6,4v16 c0,1.1,0.9,2,2,2h8c1.1,0,2-0.9,2-2V4C18,2.9,17.1,2.01,16,2.01z M16,17H8V7h8V17z"/></g></g>
  </svg>
</template>
        