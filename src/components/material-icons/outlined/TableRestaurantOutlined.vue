
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TableRestaurantOutlined',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><path d="M21.96,9.73l-1.43-5C20.41,4.3,20.02,4,19.57,4H4.43C3.98,4,3.59,4.3,3.47,4.73l-1.43,5C1.86,10.36,2.34,11,3,11h2.2L4,20 h2l0.67-5h10.67L18,20h2l-1.2-9H21C21.66,11,22.14,10.36,21.96,9.73z M6.93,13l0.27-2h9.6l0.27,2H6.93z M4.33,9l0.86-3h13.63 l0.86,3H4.33z"/></g></g>
  </svg>
</template>
        