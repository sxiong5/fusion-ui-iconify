
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BrowserNotSupportedRound',
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
    <g><rect fill="none" height="24" width="24"/><rect fill="none" height="24" width="24"/></g><g><g><path d="M19,6v10.5l1.95,1.95C20.98,18.3,21,18.15,21,18V6c0-1.1-0.9-2-2-2H6.5l2,2H19z"/><path d="M3.86,3.95c-0.35-0.35-0.92-0.35-1.27,0c-0.35,0.35-0.35,0.92,0,1.27L3,5.64L3,18c0,1.1,0.9,2,2,2h12.36l1.42,1.42 c0.35,0.35,0.92,0.35,1.27,0c0.35-0.35,0.35-0.92,0-1.27L3.86,3.95z M5,18V7.64L15.36,18H5z"/></g></g>
  </svg>
</template>
        