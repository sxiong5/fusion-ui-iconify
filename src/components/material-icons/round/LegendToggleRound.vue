
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'LegendToggleRound',
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
    <g><rect fill="none" height="24" width="24"/><path d="M19,15H5c-0.55,0-1-0.45-1-1v0c0-0.55,0.45-1,1-1h14c0.55,0,1,0.45,1,1v0C20,14.55,19.55,15,19,15z M19,17H5 c-0.55,0-1,0.45-1,1v0c0,0.55,0.45,1,1,1h14c0.55,0,1-0.45,1-1v0C20,17.45,19.55,17,19,17z M15,11l4.58-3.25 C19.84,7.56,20,7.26,20,6.94v0c0-0.81-0.92-1.29-1.58-0.82L15,8.55L10,5L4.48,8.36C4.18,8.55,4,8.87,4,9.22v0 c0,0.78,0.85,1.26,1.52,0.85l4.4-2.68L15,11z"/></g>
  </svg>
</template>
        