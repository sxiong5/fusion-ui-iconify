
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FitScreenRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><path d="M18,4h2c1.1,0,2,0.9,2,2v2c0,0.55-0.45,1-1,1h0c-0.55,0-1-0.45-1-1V6h-2c-0.55,0-1-0.45-1-1v0C17,4.45,17.45,4,18,4z M4,8 l0-2h2c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1H4C2.9,4,2,4.9,2,6l0,2c0,0.55,0.45,1,1,1h0C3.55,9,4,8.55,4,8z M20,16v2h-2 c-0.55,0-1,0.45-1,1v0c0,0.55,0.45,1,1,1h2c1.1,0,2-0.9,2-2v-2c0-0.55-0.45-1-1-1h0C20.45,15,20,15.45,20,16z M6,18H4v-2 c0-0.55-0.45-1-1-1h0c-0.55,0-1,0.45-1,1v2c0,1.1,0.9,2,2,2h2c0.55,0,1-0.45,1-1v0C7,18.45,6.55,18,6,18z M16,8H8c-1.1,0-2,0.9-2,2 v4c0,1.1,0.9,2,2,2h8c1.1,0,2-0.9,2-2v-4C18,8.9,17.1,8,16,8z"/></g>
  </svg>
</template>
        