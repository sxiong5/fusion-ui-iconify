
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BabyChangingStationSharp',
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
    <g><rect fill="none" height="24" width="24"/><path d="M14,8v2h-3L8.31,8.82L7,12.75V22H3V12l1.58-4.63C4.86,6.53,5.63,6.01,6.46,6C6.74,6,7.02,6.05,7.3,6.18l4.15,1.83L14,8z M8,1C6.9,1,6,1.9,6,3s0.9,2,2,2s2-0.9,2-2S9.1,1,8,1z M9,19h12v-2H9V19z M19.5,16c0.83,0,1.5-0.67,1.5-1.5 c0-0.83-0.67-1.5-1.5-1.5S18,13.67,18,14.5C18,15.33,18.67,16,19.5,16z M13,13v-2H9v2h2v3h6v-5h-2v2H13z"/></g>
  </svg>
</template>
        