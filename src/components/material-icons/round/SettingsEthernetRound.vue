
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SettingsEthernetRound',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M7.71,6.71L7.71,6.71c-0.39-0.39-1.02-0.39-1.41,0l-4.59,4.59c-0.39,0.39-0.39,1.02,0,1.41l4.59,4.59 c0.39,0.39,1.02,0.39,1.41,0l0,0c0.39-0.39,0.39-1.02,0-1.41L3.83,12l3.88-3.88C8.09,7.73,8.09,7.09,7.71,6.71z M16.29,6.71 L16.29,6.71c-0.39,0.39-0.39,1.02,0,1.41L20.17,12l-3.88,3.88c-0.39,0.39-0.39,1.02,0,1.41l0,0c0.39,0.39,1.02,0.39,1.41,0 l4.59-4.59c0.39-0.39,0.39-1.02,0-1.41l-4.59-4.59C17.32,6.32,16.68,6.32,16.29,6.71z M8,13L8,13c0.55,0,1-0.45,1-1v0 c0-0.55-0.45-1-1-1h0c-0.55,0-1,0.45-1,1v0C7,12.55,7.45,13,8,13z M12,13L12,13c0.55,0,1-0.45,1-1v0c0-0.55-0.45-1-1-1h0 c-0.55,0-1,0.45-1,1v0C11,12.55,11.45,13,12,13z M16,11L16,11c-0.55,0-1,0.45-1,1v0c0,0.55,0.45,1,1,1h0c0.55,0,1-0.45,1-1v0 C17,11.45,16.55,11,16,11z"/></g>
  </svg>
</template>
        