
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AlignHorizontalLeftRound',
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
    <rect fill="none" height="24" width="24"/><path d="M3,22L3,22c-0.55,0-1-0.45-1-1V3c0-0.55,0.45-1,1-1h0c0.55,0,1,0.45,1,1v18C4,21.55,3.55,22,3,22z M20.5,7h-13 C6.67,7,6,7.67,6,8.5v0C6,9.33,6.67,10,7.5,10h13c0.83,0,1.5-0.67,1.5-1.5v0C22,7.67,21.33,7,20.5,7z M14.5,14h-7 C6.67,14,6,14.67,6,15.5v0C6,16.33,6.67,17,7.5,17h7c0.83,0,1.5-0.67,1.5-1.5v0C16,14.67,15.33,14,14.5,14z"/>
  </svg>
</template>
        