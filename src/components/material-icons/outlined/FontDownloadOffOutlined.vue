
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'FontDownloadOffOutlined',
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
    <rect fill="none" height="24" width="24"/><path d="M4.83,2H20c1.1,0,2,0.9,2,2v15.17l-2-2V4H6.83L4.83,2z M10.92,6l-0.57,1.52l1.36,1.36l0.23-0.66h0.1l0.54,1.52l3.04,3.04 L13.07,6H10.92z M20.49,23.31L19.17,22H4c-1.1,0-2-0.9-2-2V4.83L0.69,3.51L2.1,2.1l19.8,19.8L20.49,23.31z M17.17,20l-5.07-5.07 H9.58L8.49,18H6.41l2.39-6.37L4,6.83V20H17.17z"/>
  </svg>
</template>
        