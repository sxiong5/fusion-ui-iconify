
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AddReactionRound',
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
    <rect fill="none" height="24" width="24"/><path d="M24,4c0,0.55-0.45,1-1,1h-1v1c0,0.55-0.45,1-1,1s-1-0.45-1-1V5h-1c-0.55,0-1-0.45-1-1c0-0.55,0.45-1,1-1h1V2 c0-0.55,0.45-1,1-1s1,0.45,1,1v1h1C23.55,3,24,3.45,24,4z M21.52,8.95C21.83,9.91,22,10.94,22,12c0,5.52-4.48,10-10,10S2,17.52,2,12 C2,6.48,6.48,2,12,2c1.5,0,2.92,0.34,4.2,0.94C16.08,3.27,16,3.62,16,4c0,1.35,0.9,2.5,2.13,2.87C18.5,8.1,19.65,9,21,9 C21.18,9,21.35,8.98,21.52,8.95z M7,9.5C7,10.33,7.67,11,8.5,11S10,10.33,10,9.5S9.33,8,8.5,8S7,8.67,7,9.5z M16.31,14H7.69 c-0.38,0-0.63,0.42-0.44,0.75C8.2,16.39,9.97,17.5,12,17.5s3.8-1.11,4.75-2.75C16.94,14.42,16.7,14,16.31,14z M17,9.5 C17,8.67,16.33,8,15.5,8S14,8.67,14,9.5s0.67,1.5,1.5,1.5S17,10.33,17,9.5z"/>
  </svg>
</template>
        