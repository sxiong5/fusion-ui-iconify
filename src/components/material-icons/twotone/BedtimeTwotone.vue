
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'BedtimeTwotone',
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
    <g><rect fill="none" height="24" width="24"/></g><g><g><g opacity=".3"><path d="M9.27 4.49C6.2 5.6 4 8.55 4 12c0 4.41 3.59 8 8 8 1.81 0 3.54-.62 4.93-1.71-3.91-1.39-9.29-6.26-7.66-13.8z"/></g><path d="M12.34 2.02c-.12 0-.23-.01-.35-.01C6.4 2.01 2 6.54 2 12c0 5.52 4.48 10 10 10 3.71 0 6.93-2.02 8.66-5.02-7.51-.25-12.09-8.43-8.32-14.96zM12 20c-4.41 0-8-3.59-8-8 0-3.45 2.2-6.4 5.27-7.51-1.63 7.54 3.75 12.41 7.66 13.8C15.54 19.38 13.81 20 12 20z"/></g></g>
  </svg>
</template>
        