
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SendTimeExtensionSharp',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M20,4h-6c0-1.38-1.12-2.5-2.5-2.5S9,2.62,9,4H3.01v5.8C5.7,9.8,6,11.96,6,12.5c0,0.54-0.29,2.7-3,2.7V21h5.8 c0-2.16,1.37-2.78,2.2-2.94v-9.3l9,4.5V4z"/><polygon points="13,12 13,16 17,17 13,18 13,22 23,17"/></g></g>
  </svg>
</template>
        