
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ToysSharp',
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
    <g display="none"><rect display="inline" fill="none" height="24" width="24" y="0"/></g><g><path d="M18.72,10l-2-6H7.28L5.81,8.4L4.41,7l1-1L4,4.59L0.59,8L2,9.41l1-1L4.59,10H2v8h2.18C4.59,19.16,5.7,20,7,20 c1.3,0,2.4-0.84,2.82-2h4.37c0.41,1.16,1.51,2,2.82,2c1.3,0,2.41-0.84,2.82-2H22v-8H18.72z M7,18c-0.55,0-1-0.45-1-1s0.45-1,1-1 s1,0.45,1,1S7.55,18,7,18z M11,10H7.41L7.39,9.98L8.72,6c0,0,0,0,0,0H11V10z M13,10V6h2.28l1.33,4H13z M17,18c-0.55,0-1-0.45-1-1 s0.45-1,1-1s1,0.45,1,1S17.55,18,17,18z"/></g>
  </svg>
</template>
        