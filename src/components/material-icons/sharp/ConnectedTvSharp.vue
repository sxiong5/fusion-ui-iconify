
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ConnectedTvSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M8.57,16H10c0-2.76-2.24-5-5-5v1.43C6.97,12.43,8.57,14.03,8.57,16z"/><path d="M11.55,16H13c0-4.42-3.59-8-8-8v1.45C8.61,9.45,11.55,12.38,11.55,16z"/><path d="M5,14v2h2C7,14.89,6.11,14,5,14z"/><path d="M22,3H2v16h6v2h8v-2h6V3z M20,17H4V5h16V17z"/></g></g>
  </svg>
</template>
        