
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'CopyAllOutlined',
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
    <rect fill="none" height="24" width="24"/><path d="M18,2H9C7.9,2,7,2.9,7,4v12c0,1.1,0.9,2,2,2h9c1.1,0,2-0.9,2-2V4C20,2.9,19.1,2,18,2z M18,16H9V4h9V16z M3,15v-2h2v2H3z M3,9.5h2v2H3V9.5z M10,20h2v2h-2V20z M3,18.5v-2h2v2H3z M5,22c-1.1,0-2-0.9-2-2h2V22z M8.5,22h-2v-2h2V22z M13.5,22L13.5,22l0-2h2 v0C15.5,21.1,14.6,22,13.5,22z M5,6L5,6l0,2H3v0C3,6.9,3.9,6,5,6z"/>
  </svg>
</template>
        