
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BabyChangingStationRound',
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
    <g><rect fill="none" height="24" width="24"/><path d="M14,9L14,9c0,0.55-0.45,1-1,1h-1.58c-0.28,0-0.55-0.06-0.8-0.17l-2.3-1.01L7,12.75V21c0,0.55-0.45,1-1,1H4 c-0.55,0-1-0.45-1-1v-8.67c0-0.22,0.04-0.44,0.11-0.65l1.48-4.32C4.96,6.25,6.22,5.69,7.3,6.18l4.15,1.83L13,8 C13.55,8,14,8.45,14,9z M8,1C6.9,1,6,1.9,6,3s0.9,2,2,2s2-0.9,2-2S9.1,1,8,1z M10,19h10c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1H10 c-0.55,0-1,0.45-1,1v0C9,18.55,9.45,19,10,19z M19.5,16c0.83,0,1.5-0.67,1.5-1.5c0-0.83-0.67-1.5-1.5-1.5S18,13.67,18,14.5 C18,15.33,18.67,16,19.5,16z M13,12c0-0.55-0.45-1-1-1h-2c-0.55,0-1,0.45-1,1v0c0,0.55,0.45,1,1,1h1v1c0,1.1,0.9,2,2,2h2 c1.1,0,2-0.9,2-2v-2c0-0.55-0.45-1-1-1h0c-0.55,0-1,0.45-1,1v1h-2V12z"/></g>
  </svg>
</template>
        