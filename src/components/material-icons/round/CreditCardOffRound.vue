
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CreditCardOffRound',
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
    <rect fill="none" height="24" width="24"/><path d="M21.19,21.19L2.81,2.81c-0.39-0.39-1.02-0.39-1.41,0l0,0C1,3.2,1,3.83,1.39,4.22l0.84,0.84C2.09,5.34,2.01,5.66,2.01,6L2,18 c0,1.11,0.89,2,2,2h13.17l2.61,2.61c0.39,0.39,1.02,0.39,1.41,0v0C21.58,22.22,21.58,21.58,21.19,21.19z M4,12V8h1.17l4,4H4z M6.83,4H20c1.11,0,2,0.89,2,2v12c0,0.34-0.08,0.66-0.23,0.94L14.83,12H20V8h-9.17L6.83,4z"/>
  </svg>
</template>
        