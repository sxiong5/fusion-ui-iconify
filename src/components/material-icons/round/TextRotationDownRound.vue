
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'TextRotationDownRound',
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
    <path d="M0 0h24v24H0V0zm0 0h24v24H0V0zm0 0h24v24H0V0z" fill="none"/><path d="M6.35 19.65l1.79-1.79c.32-.32.1-.86-.35-.86H7V5c0-.55-.45-1-1-1s-1 .45-1 1v12h-.79c-.45 0-.67.54-.35.85l1.79 1.79c.19.2.51.2.7.01zM12.2 8.5v5l-1.6.66c-.36.15-.6.5-.6.89 0 .69.71 1.15 1.34.88l8.97-3.88c.42-.18.69-.59.69-1.05 0-.46-.27-.87-.69-1.05l-8.97-3.88c-.63-.27-1.34.2-1.34.89 0 .39.24.74.6.89l1.6.65zm6.82 2.5L14 12.87V9.13L19.02 11z"/>
  </svg>
</template>
        