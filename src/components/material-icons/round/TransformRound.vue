
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TransformRound',
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
     xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"
  >
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M21 16H9c-.55 0-1-.45-1-1V4h.79c.45 0 .67-.54.35-.85l-1.79-1.8c-.2-.2-.51-.2-.71 0l-1.79 1.8c-.31.31-.09.85.36.85H6v2H3c-.55 0-1 .45-1 1s.45 1 1 1h3v8c0 1.1.9 2 2 2h8v2h-.79c-.45 0-.67.54-.35.85l1.79 1.79c.2.2.51.2.71 0l1.79-1.79c.32-.31.09-.85-.35-.85H18v-2h3c.55 0 1-.45 1-1s-.45-1-1-1zm-5-2h2V8c0-1.1-.9-2-2-2h-6v2h5c.55 0 1 .45 1 1v5z"/>
  </svg>
</template>
        