
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ElectricMeterRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><path d="M11.73,2C7.05,2.14,3.15,6.03,3,10.71c-0.13,4.04,2.42,7.5,6,8.77V21c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v-1.06 c0.33,0.04,0.66,0.06,1,0.06s0.67-0.02,1-0.06V21c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v-1.53c3.49-1.24,6-4.57,6-8.47 C21,5.95,16.82,1.85,11.73,2z M13.54,14.71L12,16.25c-0.41,0.41-1.09,0.41-1.5,0h0c-0.41-0.41-0.41-1.09,0-1.5l0.5-0.5l-0.54-0.54 c-0.39-0.39-0.39-1.02,0-1.41L12,10.75c0.41-0.41,1.09-0.41,1.5,0l0,0c0.41,0.41,0.41,1.09,0,1.5l-0.5,0.5l0.54,0.54 C13.93,13.68,13.93,14.32,13.54,14.71z M15,9H9C8.45,9,8,8.55,8,8v0c0-0.55,0.45-1,1-1h6c0.55,0,1,0.45,1,1v0C16,8.55,15.55,9,15,9 z"/></g>
  </svg>
</template>
        