
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BakeryDiningSharp',
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
    <g><rect fill="none" height="24" width="24" y="0"/></g><g><g><g><polygon points="16.36,7.58 15.5,16.99 17,16.99 20.16,9.1"/></g><g><polygon points="3.84,9.1 7,16.99 8.5,16.99 7.64,7.58"/></g><g><polygon points="10,16.99 14,16.99 15,6 9,6"/></g><g><polygon points="20.32,12.75 18.51,17.25 20.46,18.21 22.52,16.99"/></g><g><polygon points="1.48,16.99 3.54,18.21 5.49,17.25 3.68,12.75"/></g></g></g>
  </svg>
</template>
        