
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NearMeDisabledRound',
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
    <rect fill="none" height="24" width="24"/><path d="M12,6.34l6.95-2.58c0.8-0.3,1.58,0.48,1.29,1.29L17.66,12L12,6.34z M21.9,19.07L4.93,2.1c-0.39-0.39-1.02-0.39-1.41,0 c-0.39,0.39-0.39,1.02,0,1.41l4.36,4.36l-4.2,1.56C3.27,9.59,3,9.97,3,10.4c0,0.42,0.26,0.8,0.65,0.96l6.42,2.57l2.57,6.42 C12.8,20.74,13.18,21,13.6,21c0.43,0,0.82-0.27,0.97-0.67l1.56-4.2l4.36,4.36c0.39,0.39,1.02,0.39,1.41,0 C22.29,20.09,22.29,19.46,21.9,19.07z"/>
  </svg>
</template>
        