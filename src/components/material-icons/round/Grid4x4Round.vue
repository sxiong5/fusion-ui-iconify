
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'Grid4x4Round',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M22,6L22,6c0-0.55-0.45-1-1-1h-2V3c0-0.55-0.45-1-1-1h0c-0.55,0-1,0.45-1,1v2h-4V3c0-0.55-0.45-1-1-1h0 c-0.55,0-1,0.45-1,1v2H7V3c0-0.55-0.45-1-1-1h0C5.45,2,5,2.45,5,3v2H3C2.45,5,2,5.45,2,6v0c0,0.55,0.45,1,1,1h2v4H3 c-0.55,0-1,0.45-1,1v0c0,0.55,0.45,1,1,1h2v4H3c-0.55,0-1,0.45-1,1v0c0,0.55,0.45,1,1,1h2v2c0,0.55,0.45,1,1,1h0 c0.55,0,1-0.45,1-1v-2h4v2c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v-2h4v2c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v-2h2 c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h-2v-4h2c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h-2V7h2C21.55,7,22,6.55,22,6z M7,7h4v4H7 V7z M7,17v-4h4v4H7z M17,17h-4v-4h4V17z M17,11h-4V7h4V11z"/></g></g>
  </svg>
</template>
        