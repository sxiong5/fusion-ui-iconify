
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FactoryRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M14,10V8.48c0-0.71-0.71-1.19-1.37-0.93L9,9V8.52C9,7.8,8.27,7.31,7.61,7.6L3.21,9.48C2.48,9.8,2,10.52,2,11.32V20 c0,1.1,0.9,2,2,2h16c1.1,0,2-0.9,2-2V10H14z M9,17c0,0.55-0.45,1-1,1s-1-0.45-1-1v-2c0-0.55,0.45-1,1-1s1,0.45,1,1V17z M13,17 c0,0.55-0.45,1-1,1s-1-0.45-1-1v-2c0-0.55,0.45-1,1-1s1,0.45,1,1V17z M17,17c0,0.55-0.45,1-1,1s-1-0.45-1-1v-2c0-0.55,0.45-1,1-1 s1,0.45,1,1V17z"/><path d="M20.12,2h-1.23c-0.51,0-0.93,0.38-0.99,0.88L17.2,8.5h4.6l-0.69-5.62C21.05,2.38,20.62,2,20.12,2z"/></g></g>
  </svg>
</template>
        