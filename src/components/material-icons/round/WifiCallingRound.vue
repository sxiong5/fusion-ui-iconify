
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'WifiCallingRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M22,4.95C21.79,4.78,19.67,3,16.5,3c-3.18,0-5.29,1.78-5.5,1.95L16.5,12L22,4.95z"/><path d="M19.2,15.28l-2.54-0.29c-0.61-0.07-1.21,0.14-1.64,0.57l-1.84,1.84c-2.83-1.44-5.15-3.75-6.59-6.59l1.85-1.85 c0.43-0.43,0.64-1.04,0.57-1.64L8.72,4.8C8.6,3.79,7.75,3.03,6.73,3.03H5c-1.13,0-2.07,0.94-2,2.07 C3.53,13.64,10.36,20.47,18.9,21c1.13,0.07,2.07-0.87,2.07-2v-1.73C20.97,16.25,20.21,15.4,19.2,15.28z"/></g></g>
  </svg>
</template>
        