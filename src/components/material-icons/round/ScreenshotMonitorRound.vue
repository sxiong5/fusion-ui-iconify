
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ScreenshotMonitorRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M20,3H4C2.9,3,2,3.9,2,5v12c0,1.1,0.89,2,2,2h4v1c0,0.55,0.45,1,1,1h6c0.55,0,1-0.45,1-1v-1h4c1.1,0,2-0.9,2-2V5 C22,3.89,21.1,3,20,3z M20,17H4V5h16V17z"/><path d="M6.5,7.5h1.75C8.66,7.5,9,7.16,9,6.75v0C9,6.34,8.66,6,8.25,6H6C5.45,6,5,6.45,5,7v2.25C5,9.66,5.34,10,5.75,10h0 C6.16,10,6.5,9.66,6.5,9.25V7.5z"/><path d="M18.25,12L18.25,12c-0.41,0-0.75,0.34-0.75,0.75v1.75h-1.75c-0.41,0-0.75,0.34-0.75,0.75v0c0,0.41,0.34,0.75,0.75,0.75H18 c0.55,0,1-0.45,1-1v-2.25C19,12.34,18.66,12,18.25,12z"/></g></g>
  </svg>
</template>
        