
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'DeveloperBoardOffRound',
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
    <rect fill="none" height="24" width="24"/><g><path d="M7.83,5H18v10.17L19.83,17H21c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h-1v-2h1c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h-1V9 h1c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h-1V5c0-1.1-0.9-2-2-2H5.83L7.83,5z M15,10h-2c-0.06,0-0.13-0.01-0.19-0.02l-0.79-0.79 C12.01,9.13,12,9.06,12,9V8c0-0.55,0.45-1,1-1h2c0.55,0,1,0.45,1,1v1C16,9.55,15.55,10,15,10z M11,8v0.17L9.83,7H10 C10.55,7,11,7.45,11,8z M16,12v1.17L13.83,11H15C15.55,11,16,11.45,16,12z M1.39,2.81L1.39,2.81C1,3.2,1,3.83,1.39,4.22l0.61,0.61 C2,4.89,2,4.94,2,5v14c0,1.1,0.9,2,2,2h14c0.06,0,0.11,0,0.16-0.01l1.61,1.61c0.39,0.39,1.02,0.39,1.41,0l0,0 c0.39-0.39,0.39-1.02,0-1.41L2.81,2.81C2.42,2.42,1.78,2.42,1.39,2.81z M4,19V6.83l2,2V11c0,0.55,0.45,1,1,1h2.17l1.02,1.02 C10.13,13.01,10.06,13,10,13H7c-0.55,0-1,0.45-1,1v2c0,0.55,0.45,1,1,1h3c0.55,0,1-0.45,1-1v-2c0-0.06-0.01-0.13-0.02-0.19 L12,14.83v0.46V16c0,0.55,0.45,1,1,1h0.38h0.8l2,2H4z"/></g>
  </svg>
</template>
        