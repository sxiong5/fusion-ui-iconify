
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'ConveyorBeltFilled',
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
    <g><rect fill="none" height="24" width="24"/></g><g><path d="M19 15H5c-1.66 0-3 1.34-3 3s1.34 3 3 3h14c1.66 0 3-1.34 3-3s-1.34-3-3-3zm0 4H5c-.55 0-1-.45-1-1s.45-1 1-1h14c.55 0 1 .45 1 1s-.45 1-1 1zM9 4v8c0 .55.45 1 1 1h8c.55 0 1-.45 1-1V4c0-.55-.45-1-1-1h-8c-.55 0-1 .45-1 1zm7 4h-4V6.02h4V8zM2 9.02h4.94v1.91H2V9.02zm2.01-3h2.93v1.96H4.01V6.02z"/></g>
  </svg>
</template>
        