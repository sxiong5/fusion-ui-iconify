
<script lang="ts">
import { computed } from 'vue';
import { pxToRem, svgIconProps } from '../../../utils';
import '../../../style/index.css';
export default {
  name: 'NearbyOffFilled',
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
    <g><path d="M0,0h24v24H0V0z" fill="none"/></g><g><g><path d="M21.41,13.42L18.83,16l-1.81-1.81L19.2,12L12,4.8L9.81,6.99L8,5.17l2.58-2.58c0.78-0.78,2.05-0.78,2.83,0l8,8 C22.2,11.37,22.2,12.63,21.41,13.42z M21.19,21.19l-1.41,1.41L16,18.83l-2.58,2.58c-0.78,0.78-2.05,0.78-2.83,0l-8-8 c-0.78-0.78-0.78-2.05,0-2.83L5.17,8L1.39,4.22L2.8,2.81L21.19,21.19z M14.19,17.02l-1.39-1.39l-0.8,0.8L7.58,12l0.8-0.8 l-1.4-1.39L4.8,12l7.2,7.2L14.19,17.02z M16.42,12L12,7.58l-0.8,0.8l4.42,4.42L16.42,12z"/></g></g>
  </svg>
</template>
        