
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FormatOverlineFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M19,3v2H5V3H19z M12,7c-3.87,0-7,3.13-7,7c0,3.87,3.13,7,7,7s7-3.13,7-7C19,10.13,15.87,7,12,7z M12,18.5 c-2.49,0-4.5-2.01-4.5-4.5S9.51,9.5,12,9.5s4.5,2.01,4.5,4.5S14.49,18.5,12,18.5z"/></g>
  </svg>
</template>
        