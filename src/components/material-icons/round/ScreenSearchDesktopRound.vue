
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ScreenSearchDesktopRound',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M22,19H2c-0.55,0-1,0.45-1,1c0,0.55,0.45,1,1,1h20c0.55,0,1-0.45,1-1C23,19.45,22.55,19,22,19z"/><path d="M4,18h16c1.1,0,1.99-0.9,1.99-2L22,5c0-1.1-0.9-2-2-2H4C2.9,3,2,3.9,2,5v11C2,17.1,2.9,18,4,18z M8.59,8.05 C9.87,6.18,12.45,6,13.97,7.53c1.18,1.18,1.34,3,0.47,4.36L16,13.44c0.29,0.29,0.29,0.77,0,1.06c-0.29,0.29-0.77,0.29-1.06,0 l-1.55-1.55c-1.57,1-3.76,0.64-4.87-1.11C7.79,10.7,7.83,9.17,8.59,8.05z"/><circle cx="11.5" cy="10" r="2"/></g></g>
  </svg>
</template>
        