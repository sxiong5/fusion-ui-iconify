
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ForestOutlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M24,18l-3.86-6H22L15,2l-3,4.29L9,2L2,12h1.86L0,18h7v4h4v-4h2v4h4v-4H24z M15,5.49L18.16,10h-1.68l3.86,6h-3.62l-2.57-4 H16l-2.78-3.97L15,5.49z M3.66,16l3.86-6H5.84L9,5.49L12.16,10h-1.68l3.86,6H3.66z"/></g></g>
  </svg>
</template>
        