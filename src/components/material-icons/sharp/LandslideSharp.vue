
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'LandslideSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><polygon points="15.47,13.79 12.89,12.76 6,15.05 2,13.51 2,15.61 6,16.95"/><polygon points="10.57,11.42 8,8 2,8 2,11.61 6,12.95"/><polygon points="6,19.05 2,17.72 2,22 22,22 17.03,15.38"/><polygon points="17,6 17,1 12,0 9,2 9,6 12,8"/><polygon points="18.5,7 16,9 16,12 18.5,14 23,12 23,8"/></g></g>
  </svg>
</template>
        