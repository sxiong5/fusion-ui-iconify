
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NetworkLockedSharp',
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
    <path d="M0 0h24v24H0V0zm0 0h24v24H0V0z" fill="none"/><path d="M22 16v-.36c0-1.31-.94-2.5-2.24-2.63-1.5-.15-2.76 1.02-2.76 2.49v.5h-1v6h7v-6h-1zm-1 0h-3v-.5c0-.83.67-1.5 1.5-1.5s1.5.67 1.5 1.5v.5zm-1.5-5c.15 0 .3.01.46.02.01 0 .03.01.04.01V1L1 20h13v-6h1.26c.22-.63.58-1.2 1.06-1.68.85-.85 1.98-1.32 3.18-1.32z"/>
  </svg>
</template>
        