
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NewLabelRound',
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
    <rect fill="none" height="24" width="24"/><path d="M20.18,13.16l-3.55,5C16.25,18.69,15.65,19,15,19h-3l0-2l0-1c0-1.66-1.34-3-3-3h0v0c0-1.66-1.34-3-3-3H3V7c0-1.1,0.9-2,2-2 h10c0.65,0,1.26,0.31,1.63,0.84l3.55,5C20.67,11.54,20.67,12.46,20.18,13.16z M10,16c0-0.55-0.45-1-1-1H7v-2c0-0.55-0.45-1-1-1 c-0.55,0-1,0.45-1,1v2H3c-0.55,0-1,0.45-1,1c0,0.55,0.45,1,1,1h2v2c0,0.55,0.45,1,1,1c0.55,0,1-0.45,1-1v-2h2 C9.55,17,10,16.55,10,16z"/>
  </svg>
</template>
        