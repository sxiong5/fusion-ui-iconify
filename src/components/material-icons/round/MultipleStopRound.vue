
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MultipleStopRound',
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
    <g><rect fill="none" height="24" width="24"/><path d="M17,5.21c0-0.45,0.54-0.67,0.85-0.35l2.79,2.79c0.2,0.2,0.2,0.51,0,0.71l-2.79,2.79C17.54,11.46,17,11.24,17,10.79V9h-3 c-0.55,0-1-0.45-1-1v0c0-0.55,0.45-1,1-1h3V5.21z M10,7C9.45,7,9,7.45,9,8s0.45,1,1,1s1-0.45,1-1S10.55,7,10,7z M6,7 C5.45,7,5,7.45,5,8s0.45,1,1,1s1-0.45,1-1S6.55,7,6,7z M7,17h3c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1H7v-1.79 c0-0.45-0.54-0.67-0.85-0.35l-2.79,2.79c-0.2,0.2-0.2,0.51,0,0.71l2.79,2.79C6.46,19.46,7,19.24,7,18.79V17z M14,17 c0.55,0,1-0.45,1-1c0-0.55-0.45-1-1-1s-1,0.45-1,1C13,16.55,13.45,17,14,17z M18,17c0.55,0,1-0.45,1-1c0-0.55-0.45-1-1-1 s-1,0.45-1,1C17,16.55,17.45,17,18,17z"/></g>
  </svg>
</template>
        