
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ScreenshotRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M17,1.01L7,1C5.9,1,5,1.9,5,3v18c0,1.1,0.9,2,2,2h10c1.1,0,2-0.9,2-2V3C19,1.9,18.1,1.01,17,1.01z M17,18H7V6h10V18z M9.5,8.5h1.75C11.66,8.5,12,8.16,12,7.75v0C12,7.34,11.66,7,11.25,7h-2.5C8.34,7,8,7.34,8,7.75v2.5C8,10.66,8.34,11,8.75,11h0 c0.41,0,0.75-0.34,0.75-0.75V8.5z M12.75,17h2.5c0.41,0,0.75-0.34,0.75-0.75v-2.5c0-0.41-0.34-0.75-0.75-0.75h0 c-0.41,0-0.75,0.34-0.75,0.75v1.75h-1.75c-0.41,0-0.75,0.34-0.75,0.75l0,0C12,16.66,12.34,17,12.75,17z"/></g></g>
  </svg>
</template>
        