
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'PolylineRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M10.04,6.85L7.3,10H4.5C3.67,10,3,10.67,3,11.5v3C3,15.33,3.67,16,4.5,16h3c0.14,0,0.27-0.02,0.39-0.05L15,19.5v1 c0,0.83,0.67,1.5,1.5,1.5h3c0.83,0,1.5-0.67,1.5-1.5v-3c0-0.83-0.67-1.5-1.5-1.5h-3c-0.75,0-1.37,0.55-1.48,1.27L9,14.26V11.5 c0-0.12-0.01-0.24-0.04-0.36L11.7,8h2.8C15.33,8,16,7.33,16,6.5v-3C16,2.67,15.33,2,14.5,2h-3C10.67,2,10,2.67,10,3.5v3 C10,6.62,10.01,6.74,10.04,6.85z"/></g>
  </svg>
</template>
        