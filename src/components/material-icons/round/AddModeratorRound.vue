
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AddModeratorRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M17,10c1.08,0,2.09,0.25,3,0.68v-4.3c0-0.83-0.52-1.58-1.3-1.87l-6-2.25c-0.45-0.17-0.95-0.17-1.4,0l-6,2.25 C4.52,4.81,4,5.55,4,6.39v4.7c0,5.05,3.41,9.76,8,10.91c0.03-0.01,0.05-0.02,0.08-0.02C10.8,20.71,10,18.95,10,17 C10,13.13,13.13,10,17,10z"/><path d="M17,12c-2.76,0-5,2.24-5,5s2.24,5,5,5s5-2.24,5-5S19.76,12,17,12z M19.5,17.5h-2v2c0,0.28-0.22,0.5-0.5,0.5 s-0.5-0.22-0.5-0.5v-2h-2c-0.28,0-0.5-0.22-0.5-0.5s0.22-0.5,0.5-0.5h2v-2c0-0.28,0.22-0.5,0.5-0.5s0.5,0.22,0.5,0.5v2h2 c0.28,0,0.5,0.22,0.5,0.5S19.78,17.5,19.5,17.5z"/></g></g>
  </svg>
</template>
        