
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'EventRepeatRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M21,12V6c0-1.1-0.9-2-2-2h-1V3c0-0.55-0.45-1-1-1s-1,0.45-1,1v1H8V3c0-0.55-0.45-1-1-1S6,2.45,6,3v1H5C3.9,4,3,4.9,3,6v14 c0,1.1,0.9,2,2,2h7v-2H5V10h14v2H21z M15.13,20c-0.55,0-0.91,0.56-0.68,1.06C15.23,22.79,16.97,24,19,24c2.76,0,5-2.24,5-5 s-2.24-5-5-5c-1.36,0-2.6,0.55-3.5,1.43l0-0.68c0-0.41-0.34-0.75-0.75-0.75h0C14.34,14,14,14.34,14,14.75V17c0,0.55,0.45,1,1,1 h2.25c0.41,0,0.75-0.34,0.75-0.75v0c0-0.41-0.34-0.75-0.75-0.75l-0.7,0c0.63-0.62,1.5-1,2.45-1c1.93,0,3.5,1.57,3.5,3.5 s-1.57,3.5-3.5,3.5c-1.42,0-2.64-0.85-3.19-2.06C15.69,20.17,15.42,20,15.13,20z"/></g>
  </svg>
</template>
        