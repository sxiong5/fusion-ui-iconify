
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'PhoneEnabledTwotone',
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
    <rect fill="none" height="24" width="24"/><g><g><path d="M21,4c0,9.39-7.61,17-17,17c-0.55,0-1-0.45-1-1v-3.49c0-0.55,0.45-1,1-1c1.24,0,2.45-0.2,3.57-0.57 c0.1-0.04,0.21-0.05,0.31-0.05c0.26,0,0.51,0.1,0.71,0.29l2.2,2.2c2.83-1.45,5.15-3.76,6.59-6.59l-2.2-2.2 c-0.28-0.28-0.36-0.67-0.25-1.02C15.3,6.45,15.5,5.25,15.5,4c0-0.55,0.45-1,1-1H20C20.55,3,21,3.45,21,4z M7.6,17.02 c-0.85,0.24-1.72,0.39-2.6,0.45v1.49c1.32-0.09,2.59-0.35,3.8-0.75L7.6,17.02z M17.46,5c-0.06,0.89-0.21,1.76-0.45,2.59l1.2,1.2 c0.41-1.2,0.67-2.47,0.76-3.79H17.46z"/></g></g>
  </svg>
</template>
        