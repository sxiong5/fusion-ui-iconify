
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'RememberMeOutlined',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M17,1H7C5.9,1,5,1.9,5,3v18c0,1.1,0.9,2,2,2h10c1.1,0,2-0.9,2-2V3C19,1.9,18.1,1,17,1z M17,21H7v-1h10V21z M17,18H7v-0.48 C8.47,16.53,10.22,16,12,16s3.53,0.53,5,1.52V18z M17,15.21C15.5,14.44,13.8,14,12,14s-3.5,0.44-5,1.21V6h10V15.21z M17,4H7V3h10 V4z"/><path d="M12,13c1.66,0,3-1.34,3-3s-1.34-3-3-3s-3,1.34-3,3S10.34,13,12,13z M12,9c0.55,0,1,0.45,1,1s-0.45,1-1,1s-1-0.45-1-1 S11.45,9,12,9z"/></g></g>
  </svg>
</template>
        