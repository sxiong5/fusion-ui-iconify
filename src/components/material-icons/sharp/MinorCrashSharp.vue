
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'MinorCrashSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M18.57,8H5.43L3,15v9h3v-2h12v2h3v-9L18.57,8z M6.85,10h10.29l1.04,3H5.81L6.85,10z M6,17.5C6,16.67,6.67,16,7.5,16 S9,16.67,9,17.5S8.33,19,7.5,19S6,18.33,6,17.5z M15,17.5c0-0.83,0.67-1.5,1.5-1.5s1.5,0.67,1.5,1.5S17.33,19,16.5,19 S15,18.33,15,17.5z M9.41,5L8,6.41l-3-3L6.41,2L9.41,5z M16,6.41L14.59,5l3-3L19,3.41L16,6.41z M13,5h-2V0h2V5z"/></g>
  </svg>
</template>
        