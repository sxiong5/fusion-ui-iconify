
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'PhotoSizeSelectSmallSharp',
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
    <path d="M0 0h24v24H0V0z" fill="none"/><path d="M23 15h-2v2h2v-2zm0 4h-2v2h2v-2zm0-8h-2v2h2v-2zm-8-8h-2v2h2V3zm8 4h-2v2h2V7zM1 21h10v-6H1v6zM3 7H1v2h2V7zm12 12h-2v2h2v-2zm4-16h-2v2h2V3zm4 0h-2v2h2V3zm-4 16h-2v2h2v-2zM3 11H1v2h2v-2zm8-8H9v2h2V3zM7 3H5v2h2V3zM3 3H1v2h2V3z"/>
  </svg>
</template>
        