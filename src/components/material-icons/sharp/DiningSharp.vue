
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DiningSharp',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><path d="M22,2H2v20h20V2z M11,10.3c0,0.93-0.64,1.71-1.5,1.93V19H8v-6.77c-0.86-0.22-1.5-1-1.5-1.93V6H7h0.5v3h0.75V6h0.5h0.5v3H10 V6h0.5H11V10.3z M15.58,12.59l-0.08,0.03V19H14v-6.38l-0.08-0.04c-0.97-0.47-1.67-1.7-1.67-3.18c0-1.88,1.13-3.4,2.5-3.4 c1.38,0,2.5,1.53,2.5,3.41C17.25,10.89,16.55,12.12,15.58,12.59z"/></g>
  </svg>
</template>
        