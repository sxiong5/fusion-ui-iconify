
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CoffeeRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><path d="M18.5,3H6C4.9,3,4,3.9,4,5v5.71c0,3.83,2.95,7.18,6.78,7.29c3.96,0.12,7.22-3.06,7.22-7v-1h0.5c1.93,0,3.5-1.57,3.5-3.5 S20.43,3,18.5,3z M16,5v3H6V5H16z M18.5,8H18V5h0.5C19.33,5,20,5.67,20,6.5S19.33,8,18.5,8z M5,19h14c0.55,0,1,0.45,1,1v0 c0,0.55-0.45,1-1,1H5c-0.55,0-1-0.45-1-1v0C4,19.45,4.45,19,5,19z"/></g>
  </svg>
</template>
        