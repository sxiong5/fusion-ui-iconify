
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'RsvpSharp',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M16,9h1.5l-1.75,6h-1.5L12.5,9H14l1,3.43L16,9z M5.14,13L6,15H4.5l-0.85-2H2.5v2H1V9h5v4L5.14,13z M4.5,10.5h-2v1h2V10.5z M23,13h-3.5v2H18V9h5V13z M21.5,10.5h-2v1h2V10.5z M11.5,9v1.5h-3v0.75h3V15H7v-1.5h3v-0.75H7V9H11.5z"/></g></g>
  </svg>
</template>
        