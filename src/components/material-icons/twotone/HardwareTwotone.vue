
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'HardwareTwotone',
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
    <g><rect fill="none" height="24" width="24" y="0"/></g><g><g><path d="M6.77,6H11v5h2V5H9C8.11,5,7.32,5.39,6.77,6z" enable-background="new" opacity=".3"/><rect enable-background="new" height="6" opacity=".3" width="2" x="11" y="13"/><path d="M18,3l-3,3V3H9C6.24,3,4,5.24,4,8h5v12c0,0.55,0.45,1,1,1h4c0.55,0,1-0.45,1-1V8l3,3h2V3H18z M13,19h-2v-6h2V19z M13,11 h-2V6H6.77C7.32,5.39,8.11,5,9,5h4V11z"/></g></g>
  </svg>
</template>
        