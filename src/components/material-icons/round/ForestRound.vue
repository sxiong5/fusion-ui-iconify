
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ForestRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M14.14,12h-0.06c0.81,0,1.28-0.91,0.82-1.57L9.82,3.17c-0.4-0.57-1.24-0.57-1.64,0L3.1,10.43C2.64,11.09,3.11,12,3.92,12 H3.86l-2.87,4.46C0.56,17.12,1.04,18,1.83,18H7v2c0,1.1,0.9,2,2,2s2-0.9,2-2v-2h5.17c0.79,0,1.27-0.88,0.84-1.54L14.14,12z"/><path d="M23.01,16.46L20.14,12h-0.06c0.81,0,1.28-0.91,0.82-1.57l-5.08-7.26c-0.4-0.57-1.24-0.57-1.64,0l-1.57,2.24l3.11,4.44 c0.43,0.61,0.48,1.41,0.14,2.07c-0.08,0.16-0.18,0.3-0.3,0.43l2.29,3.57c0.4,0.62,0.42,1.4,0.07,2.04 c-0.01,0.02-0.02,0.03-0.03,0.04h4.28C22.96,18,23.44,17.12,23.01,16.46z"/><path d="M13,20c0,1.1,0.9,2,2,2s2-0.9,2-2v-1h-4V20z"/></g></g>
  </svg>
</template>
        