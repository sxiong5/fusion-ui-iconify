
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'LightRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><path d="M13,6.06V4c0-0.55-0.45-1-1-1h0c-0.55,0-1,0.45-1,1v2.06c-4.5,0.5-8,4.31-8,8.93C3,16.1,3.9,17,5.01,17L8,17 c0,2.21,1.79,4,4,4s4-1.79,4-4l2.99,0C20.1,17,21,16.1,21,14.99C21,10.37,17.5,6.56,13,6.06z M12,15l-7,0c0-3.86,3.14-7,7-7 s7,3.14,7,7L12,15z"/></g>
  </svg>
</template>
        