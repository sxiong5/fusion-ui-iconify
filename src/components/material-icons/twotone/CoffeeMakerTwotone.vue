
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CoffeeMakerTwotone',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><g><path d="M13,19c1.65,0,3-1.35,3-3v-3h-6v3C10,17.65,11.35,19,13,19z" opacity=".3"/><path d="M9,7h8c0.55,0,1-0.45,1-1V4h2V2H6C4.9,2,4,2.9,4,4v16c0,1.1,0.9,2,2,2h14v-2h-4.03C17.2,19.09,18,17.64,18,16v-5H8v5 c0,1.64,0.81,3.09,2.03,4H6V4h2v2C8,6.55,8.45,7,9,7z M10,16v-3h6v3c0,1.65-1.35,3-3,3S10,17.65,10,16z"/></g><circle cx="13" cy="9" r="1"/></g></g>
  </svg>
</template>
        