
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'SnippetFolderRound',
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
    <g><rect fill="none" height="24" width="24"/><path d="M15.88,10.5l1.62,1.62v3.38l-3,0v-5H15.88z M22,8v10c0,1.1-0.9,2-2,2H4c-1.1,0-2-0.9-2-2L2.01,6C2.01,4.9,2.9,4,4,4h5.17 c0.53,0,1.04,0.21,1.41,0.59L12,6h8C21.1,6,22,6.9,22,8z M19,11.91c0-0.27-0.11-0.52-0.29-0.71l-1.91-1.91 C16.61,9.11,16.35,9,16.09,9H14c-0.55,0-1,0.45-1,1v6c0,0.55,0.45,1,1,1l4,0c0.55,0,1-0.45,1-1V11.91z"/></g>
  </svg>
</template>
        