
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'EditOffRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><g><path d="M2.1,3.51L2.1,3.51c-0.39,0.39-0.39,1.02,0,1.41l6.61,6.61L3.15,17.1C3.05,17.2,3,17.32,3,17.46v3.04 C3,20.78,3.22,21,3.5,21h3.04c0.13,0,0.26-0.05,0.35-0.15l5.56-5.56l6.61,6.61c0.39,0.39,1.02,0.39,1.41,0l0,0 c0.39-0.39,0.39-1.02,0-1.41L3.52,3.51C3.12,3.12,2.49,3.12,2.1,3.51z"/></g><g><path d="M20.71,7.04c0.39-0.39,0.39-1.02,0-1.41l-2.34-2.34c-0.39-0.39-1.02-0.39-1.41,0l-1.83,1.83l3.75,3.75L20.71,7.04z"/></g><g><rect height="5.3" transform="matrix(0.7071 -0.7071 0.7071 0.7071 -2.2957 13.1079)" width="3.56" x="12.89" y="6.67"/></g></g></g>
  </svg>
</template>
        