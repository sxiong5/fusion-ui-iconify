
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ModeOfTravelRound',
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
    <rect fill="none" height="24" width="24"/><path d="M4,10.2C4,5.22,7.8,2,12,2c4,0,7.64,2.92,7.97,7.5l2.32,0c0.45,0,0.67,0.54,0.35,0.85l-3.29,3.29c-0.2,0.2-0.51,0.2-0.71,0 l-3.29-3.29c-0.31-0.31-0.09-0.85,0.35-0.85l2.26,0C17.65,6.24,15.13,4,12,4c-3.35,0-6,2.57-6,6.2c0,2.34,1.95,5.44,6,9.14 c0.64-0.59,1.23-1.16,1.77-1.71c-0.17-0.34-0.27-0.72-0.27-1.12c0-1.38,1.12-2.5,2.5-2.5s2.5,1.12,2.5,2.5S17.38,19,16,19 c-0.24,0-0.47-0.03-0.69-0.1c-0.78,0.82-1.67,1.66-2.65,2.52c-0.38,0.33-0.95,0.33-1.33,0C6.45,17.12,4,13.38,4,10.2z"/>
  </svg>
</template>
        