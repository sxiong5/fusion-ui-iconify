
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'RepeatOnRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M21,1H3C1.9,1,1,1.9,1,3v18c0,1.1,0.9,2,2,2h18c1.1,0,2-0.9,2-2V3C23,1.9,22.1,1,21,1z M19,18c0,0.55-0.45,1-1,1H7v1.79 c0,0.45-0.54,0.67-0.85,0.36l-2.79-2.79c-0.2-0.2-0.2-0.51,0-0.71l2.79-2.79C6.46,14.54,7,14.76,7,15.21V17h10v-3 c0-0.55,0.45-1,1-1s1,0.45,1,1V18z M20.64,6.35l-2.79,2.79C17.54,9.46,17,9.24,17,8.79V7H7v3c0,0.55-0.45,1-1,1s-1-0.45-1-1V6 c0-0.55,0.45-1,1-1h11V3.21c0-0.45,0.54-0.67,0.85-0.36l2.79,2.79C20.84,5.84,20.84,6.15,20.64,6.35z"/></g>
  </svg>
</template>
        