
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'IceSkatingFilled',
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
    <rect fill="none" height="24" width="24"/><g><path d="M8,8.5C8,8.22,8.22,8,8.5,8h2.52L11,7H8.5C8.22,7,8,6.78,8,6.5C8,6.22,8.22,6,8.5,6H11V3H3v15h3v2H2v2h16 c2.76,0,5-2.24,5-5h-2c0,1.66-1.34,3-3,3h-2v-2h3l0-2.88c0-2.1-1.55-3.53-3.03-3.88l-2.7-0.67C12.4,10.35,11.7,9.76,11.32,9H8.5 C8.22,9,8,8.78,8,8.5z M14,20H8v-2h6V20z"/></g>
  </svg>
</template>
        