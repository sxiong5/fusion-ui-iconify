
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CastleRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M22,9c-0.55,0-1,0.45-1,1v1h-2V4c0-0.55-0.45-1-1-1s-1,0.45-1,1v1h-2V4c0-0.55-0.45-1-1-1s-1,0.45-1,1v1h-2V4 c0-0.55-0.45-1-1-1S9,3.45,9,4v1H7V4c0-0.55-0.45-1-1-1S5,3.45,5,4v7H3v-1c0-0.55-0.45-1-1-1s-1,0.45-1,1v9c0,1.1,0.9,2,2,2h7v-3 c0-1.1,0.9-2,2-2s2,0.9,2,2v3h7c1.1,0,2-0.9,2-2v-9C23,9.45,22.55,9,22,9z M11,12H9V9h2V12z M15,12h-2V9h2V12z"/></g></g>
  </svg>
</template>
        