
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ResetTvRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><path d="M20,10h-7.01V8.21c0-0.45-0.54-0.67-0.85-0.35l-2.78,2.79c-0.19,0.2-0.19,0.51,0,0.71l2.78,2.79 c0.31,0.32,0.85,0.09,0.85-0.35V12H20v5H4V5h16v2c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1l0-2c0-1.1-0.9-2-2-2H4C2.9,3,2,3.9,2,5v12 c0,1.1,0.9,2,2,2h4v1c0,0.55,0.45,1,1,1h6c0.55,0,1-0.45,1-1v-1h4c1.1,0,2-0.9,2-2v-5C22,10.9,21.1,10,20,10z"/></g>
  </svg>
</template>
        