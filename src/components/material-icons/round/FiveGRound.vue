
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FiveGRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M18,13h1v2h-5V9h6c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h-6c-1.1,0-2,0.9-2,2v6c0,1.1,0.9,2,2,2h5c1.1,0,2-0.9,2-2v-3 c0-0.55-0.45-1-1-1h-2c-0.55,0-1,0.45-1,1v0C17,12.55,17.45,13,18,13z"/><path d="M4,13h4v2H4c-0.55,0-1,0.45-1,1v0c0,0.55,0.45,1,1,1h4c1.1,0,2-0.9,2-2v-2c0-1.1-0.9-2-2-2H5V9h4c0.55,0,1-0.45,1-1v0 c0-0.55-0.45-1-1-1H4C3.45,7,3,7.45,3,8v4C3,12.55,3.45,13,4,13z"/></g></g>
  </svg>
</template>
        