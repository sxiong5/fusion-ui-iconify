
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BackpackRound',
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
    <g><rect fill="none" height="24" width="24"/><g><g><path d="M20,8v12c0,1.1-0.9,2-2,2H6c-1.1,0-2-0.9-2-2V8c0-1.86,1.28-3.41,3-3.86V3.5C7,2.67,7.67,2,8.5,2h0 C9.33,2,10,2.67,10,3.5V4h4V3.5C14,2.67,14.67,2,15.5,2h0C16.33,2,17,2.67,17,3.5v0.64C18.72,4.59,20,6.14,20,8z M6,13L6,13 c0,0.55,0.45,1,1,1h9v1c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v-2c0-0.55-0.45-1-1-1H7C6.45,12,6,12.45,6,13z"/></g></g></g>
  </svg>
</template>
        