
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TsunamiSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M18.67,17.63c-3.8,2.8-6.12,0.4-6.67,0c-0.66,0.49-2.92,2.76-6.67,0C3.43,19.03,2.65,19,2,19v2c1.16,0,2.3-0.32,3.33-0.93 c2.06,1.22,4.61,1.22,6.67,0c2.06,1.22,4.61,1.22,6.67,0C19.7,20.68,20.84,21,22,21v-2C21.34,19,20.5,18.98,18.67,17.63z"/><path d="M19.33,12H22v-2h-2.67C17.5,10,16,8.5,16,6.67c0-1.02,0.38-1.74,1.09-3.34C15.72,3.12,15.09,3,14,3 C7.36,3,2.15,8.03,2.01,14.5c0,0-0.01,2-0.01,2c1.16,0,2.3-0.32,3.33-0.93c2.06,1.22,4.61,1.22,6.67,0c2.06,1.22,4.61,1.22,6.67,0 c1.03,0.61,2.17,0.93,3.33,0.93v-2c-0.66,0-1.5-0.02-3.33-1.37c-3.8,2.8-6.12,0.4-6.67,0c-0.9,0.67-0.54,0.41-0.91,0.63 C10.39,12.82,10,11.7,10,10.5c0-2.58,1.77-4.74,4.21-5.33C14.08,5.68,14,6.19,14,6.67C14,9.61,16.39,12,19.33,12z"/></g></g>
  </svg>
</template>
        