
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'AlignHorizontalRightRound',
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
    <rect fill="none" height="24" width="24"/><path d="M21,2L21,2c0.55,0,1,0.45,1,1v18c0,0.55-0.45,1-1,1h0c-0.55,0-1-0.45-1-1V3C20,2.45,20.45,2,21,2z M3.5,10h13 c0.83,0,1.5-0.67,1.5-1.5v0C18,7.67,17.33,7,16.5,7h-13C2.67,7,2,7.67,2,8.5v0C2,9.33,2.67,10,3.5,10z M9.5,17h7 c0.83,0,1.5-0.67,1.5-1.5v0c0-0.83-0.67-1.5-1.5-1.5h-7C8.67,14,8,14.67,8,15.5v0C8,16.33,8.67,17,9.5,17z"/>
  </svg>
</template>
        