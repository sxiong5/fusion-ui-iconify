
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CleaningServicesRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M16,11h-1V4c0-1.66-1.34-3-3-3h0c-1.66,0-3,1.34-3,3v7H8c-2.76,0-5,2.24-5,5v5c0,1.1,0.9,2,2,2h14c1.1,0,2-0.9,2-2v-5 C21,13.24,18.76,11,16,11z M19,21h-2v-3c0-0.55-0.45-1-1-1s-1,0.45-1,1v3h-2v-3c0-0.55-0.45-1-1-1s-1,0.45-1,1v3H9v-3 c0-0.55-0.45-1-1-1s-1,0.45-1,1v3H5v-5c0-1.65,1.35-3,3-3h8c1.65,0,3,1.35,3,3V21z"/></g>
  </svg>
</template>
        