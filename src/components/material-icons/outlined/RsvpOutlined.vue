
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'RsvpOutlined',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M16,9h1.5l-1.75,6h-1.5L12.5,9H14l1,3.43L16,9z M5.1,12.9L6,15H4.5l-0.85-2H2.5v2H1V9h3.5C5.35,9,6,9.65,6,10.5v1 C6,12.1,5.6,12.65,5.1,12.9z M4.5,10.5h-2v1h2V10.5z M21.5,13h-2v2H18V9h3.5c0.83,0,1.5,0.67,1.5,1.5v1C23,12.33,22.33,13,21.5,13 z M21.5,10.5h-2v1h2V10.5z M11.5,9v1.5h-3v0.75h2c0.55,0,1,0.45,1,1V14c0,0.55-0.45,1-1,1H7v-1.5h3v-0.75H7.75 C7.34,12.75,7,12.41,7,12v-2c0-0.55,0.45-1,1-1H11.5z"/></g></g>
  </svg>
</template>
        