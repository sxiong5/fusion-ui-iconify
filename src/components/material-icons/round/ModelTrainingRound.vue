
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ModelTrainingRound',
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
    <g><rect fill="none" height="24" width="24"/><path d="M15.5,13.5c0,2-2.5,3.5-2.5,5h-2c0-1.5-2.5-3-2.5-5c0-1.93,1.57-3.5,3.5-3.5h0C13.93,10,15.5,11.57,15.5,13.5z M13,19.5h-2 V20c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1V19.5z M19,13c0,1.39-0.41,2.69-1.12,3.78c-0.25,0.39-0.19,0.91,0.14,1.24l0,0 c0.44,0.44,1.2,0.38,1.54-0.15C20.47,16.47,21,14.8,21,13c0-2.36-0.91-4.51-2.4-6.12c-0.39-0.42-1.05-0.43-1.45-0.03l0,0 c-0.38,0.38-0.38,0.99-0.02,1.39C18.29,9.49,19,11.16,19,13z M15.65,4.65l-2.79-2.79C12.54,1.54,12,1.76,12,2.21V4l0,0 c-4.97,0-9,4.03-9,9c0,1.8,0.53,3.47,1.44,4.88c0.34,0.53,1.1,0.59,1.54,0.15l0,0c0.33-0.33,0.39-0.84,0.14-1.23 C4.73,14.65,4.48,11.7,6.25,8.8C7.45,6.85,9.71,5.81,12,6l0,0v1.79c0,0.45,0.54,0.67,0.85,0.35l2.79-2.79 C15.84,5.16,15.84,4.84,15.65,4.65z"/></g>
  </svg>
</template>
        